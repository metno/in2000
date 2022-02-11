---
layout: page
title: Case 5 - Oppdrettsanlegg
date: 2022-02-09
---

Lag en app som viser miljøforhold ved et oppdrettsanlegg for laks. Oppdrettsindustrien i Norge foregår for det meste som oppdrett av laks i åpne merder i sjøen. Fisken påvirkes av det omliggende miljøet på en direkte måte. Det fysiske miljøet ved en oppdrettslokalitet, det vil si vannets saltholdighet, temperatur og bevegelse (strøm), kan variere mye fra dag til dag. Det vil være av interesse for fiskeoppdrettere å kunne få en indikasjon på hvordan miljøforholdene på anlegget deres vil endre seg de neste dagene.

Havmodellen NorKyst-800 beregner daglig nødvendige parametere på et horisontalt rutenett med 800 m oppløsning for hele landet time for time og ca. to døgn fram i tid. Andre
sammensatte parametere som tykkelsen på blandingslaget eller statistiske forhold kan være
interessant å inkludere. Det samme gjelder muligheten for å beskrive forventet smittepress fra lakselus.

## Noen ideer til inspirasjon
 * Kart med plassering av oppdrettsanlegg
 * Tidsserier av saltholdighet, temperatur og strøm fra lokaliteten
 * Tidsserier av beregnet blandingslagsdyp fra lokaliteten
 * Smittepress fra lakselus ved lokaliteten de siste ukene
 * Værvarsel ved lokaliteten

## Datakilder
Primære (obligatisk):
 * Daglige verdier av resultater fra strømmodellen NorKyst-800: <https://thredds.met.no/thredds/catalog/fou-hi/norkyst800m-1h/catalog.html>
 * Ukentlige verdier av beregnet smittepress fra lakselus basert på NorKyst-800: <http://thredds.nodc.no:8080/thredds/catalog/smittepress_new2018/catalog.html>

Sekundære (valgfritt) – se [Generelle ressurser](../general):
 * Oceanforecast

## Eksempler på spørring mot THREDDS-server hos MET
For å jobbe mot data som ligger i gitter/grid på THREDDS-servere så bruker vi protokollen OPeNDAP. Dette krever litt Java-koding, men ved å se på eksempelkoden rett nedenfor så kommer dere raskt i gang.

### Minimalt eksempel på bruk av NetCDF Java
Dette eksempelet bruker litt eldre funksjonalitet, og det er naturligvis flere måter å gjøre dette på.

Brukerdokumentasjon finnes på <https://docs.unidata.ucar.edu/netcdf-java/current/userguide/index.html> og Javadoc som også dekker pakken ucar.nc2.dt (som brukes i eksempelet nedenfor) kan finnes på <http://javadox.com/edu.ucar/netcdf/4.2/overview-summary.html>

```
import java.io.IOException;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

import ucar.ma2.Array;
import ucar.ma2.InvalidRangeException;
import ucar.nc2.NetcdfFile;
import ucar.nc2.Variable;
import ucar.nc2.dataset.NetcdfDatasets;
import ucar.nc2.dt.GridCoordSystem;
import ucar.nc2.dt.GridDataset;
import ucar.nc2.dt.GridDatatype;
import ucar.nc2.write.Ncdump;

public class TestOpendap {

    protected final Logger logger = LoggerFactory.getLogger(this.getClass());

    private void openWithNetcdfDatasets(String urlName) {

        try (NetcdfFile ncfile = NetcdfDatasets.openFile(urlName, null)) {
            // Do cool stuff here
            System.out.println("SUCCESS - OPENDAP URL OPENED");

            System.out.println(ncfile);
          
            Variable v = ncfile.findVariable("temperature");
            if (v == null)
            return;

            // direct indexing (ranges)
            // note that this way of reading does not apply scale or offset
            // see variable attributes "scale_factor" and "add_offset"
            // the argument for read(...) is specifying a range of data per dimension (order is t, z, y, x)
            Array data = v.read("2,0:2,200:203,199");
            String arrayStr = Ncdump.printArray(data, "temperature_selection", null);
            System.out.println(arrayStr);

            ncfile.close();
          } catch (IOException | InvalidRangeException e) {
            // Handle less-cool exceptions here
            logger.error("ERROR", e);
          }        
          
          NetcdfDatasets.shutdown();
    }

    private void openWithGridDataset(String urlName) {

        // open the dataset, find the variable and its coordinate system
        try (GridDataset gds = ucar.nc2.dt.grid.GridDataset.open(urlName)) {
            System.out.println("SUCCESS - OPENDAP URL OPENED");
            GridDatatype grid = gds.findGridDatatype("temperature");
            GridCoordSystem gcs = grid.getCoordinateSystem();

            double lat = 60.3;
            double lon = 4.5;

            // find the x,y index for a specific lat/lon position
            int[] xy = gcs.findXYindexFromLatLon(lat, lon, null); // xy[0] = x, xy[1] = y

            // read the data at that lat, lon and the first time and z level (if any)
            Array data = grid.readDataSlice(0, 0, xy[1], xy[0]); // note order is t, z, y, x
            double val = data.getDouble(0); // we know its a scalar
            System.out.printf("Value at %f %f == %f%n", lat, lon, val);

            // read the data at that lat, lon and the first time and all z levels/depths
            // produces a depth profile
            Array depthData = grid.readDataSlice(0, -1, xy[1], xy[0]); // note order is t, z, y, x
            System.out.println("Depth profile: " + depthData);

            // read the data at that lat, lon and the first z level and all timesteps
            // produces a time series
            Array timeSeriesData = grid.readDataSlice(-1, 0, xy[1], xy[0]); // note order is t, z, y, x
            System.out.println("Time series: " + timeSeriesData);

        } catch (IOException e) {
            // Handle less-cool exceptions here
            logger.error("ERROR", e);
        }  
    }

    public static void main(String[] args) {

        TestOpendap testodap = new TestOpendap();

        String urlName = 
        "https://thredds.met.no/thredds/dodsC/fou-hi/norkyst800m-1h/NorKyst-800m_ZDEPTHS_his.an.2022020900.nc";

        testodap.openWithNetcdfDatasets(urlName);
        
        testodap.openWithGridDataset(urlName);
    }
}
```

### Avhengigheter
 * NetCDF Java <https://www.unidata.ucar.edu/downloads/netcdf-java/>
 * SLF4J <https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.7.36/>

## Mest relevante interessenter
Havforskningsinstituttet, Eide Fjordbruk, SEARIS og andre oppdrettsselskaper.
