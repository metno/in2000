---
layout: page
title: Victoria WMS
parent: Generelle ressurser
nav_order: 25
date: 2026-02-20
author: Geir Aalberg
---


[Victoria](https://public-victoria.met.no/docs) er den nye offentlige karttjenesten fra MET, oppkalt etter det første
[skipet](https://en.wikipedia.org/wiki/Victoria_(ship)) som gjorde jordomseiling.


## WMS

Grensesnittet til Victoria er åpent uten registrering og kan finnes her:

- <https://public-victoria.met.no/docs>

For å teste, legg inn flg verdier under "GET /wms":

|Parameter|Verdi|
|---------|-----|
|service  |WMS  |
|version  |1.3.0|
|request  |GetCapabilities|
|format   |image/png|
|transparent|true|
|group    |in2000|

Evt kan dere også filtrere på `model`, flg kan være nyttige:

- meps_det_vdiv_2_5km_calculations
- arome_arctic_det_vdiv_2_5km_calculations
- ec_vdiv_1h

{: .note }
Vi anbefaler sterkt å filtrere på gruppe eller modell, da den komplette
Capabilities har 1979 lag og er på 7.6 MB som Swagger UI ikke greier å håndtere.
Komplett liste over modeller kan lastes ned på
[/get-models](https://public-victoria.met.no/get-models),
mens grupper (med tilhørende modeller) finnes på
[/get-model-groups](https://public-victoria.met.no/get-model-groups).

- [WMS Capabilities](https://public-victoria.met.no/wms?service=WMS&version=1.3.0&request=GetCapabilities&format=image%2Fpng&transparent=true&model=meps_det_vdiv_2_5km_calculations) - MEPS (calculated), 600 KB

### Kartlag

Vi anbefaler å bruke flg layers:

#### Norden

|Layer|Title|
|-----|-----|
|air_temperature_2m_meps_det_vdiv_2_5km_calculations|Air temperature 2m in MEPS VDIV|
|precipitation_amount_1h_meps_det_vdiv_2_5km_calculations|Precipitation amount 1h in MEPS VDIV|
|wind_10m_vector_meps_det_vdiv_2_5km_calculations|Wind 10m vector in MEPS VDIV|

#### Arktis

|Layer|Title|
|-----|-----|
|air_temperature_2m_arome_arctic_det_vdiv_2_5km_calculations|Air temperature 2m in Arctic VDIV|
|precipitation_amount_1h_arome_arctic_det_vdiv_2_5km_calculations|Precipitation amount 1h in Arctic VDIV|
|wind_10m_vector_arome_arctic_det_vdiv_2_5km_calculations|Wind 10m vector in Arctic VDIV|

#### Global

|Layer|Title|
|-----|-----|
|air_temperature_2m_ec_vdiv_1h_calculations|Air temperature 2m in ECMWF 1 h|
|precipitation_amount_1h_ec_vdiv_1h_calculations|Precipitation amount 1h in ECMWF 1 h|
|wind_10m_vector_ec_vdiv_1h_calculations|Wind 10m vector in ECMWF 1 h|

------------------------------------

## Layers per modell

### meps_det_vdiv_2_5km

    MS
    air_pressure_at_sea_level_meps_det_vdiv_2_5km_calculations
    air_temperature_0m_meps_det_vdiv_2_5km_calculations
    air_temperature_2m_meps_det_vdiv_2_5km_calculations
    air_temperature_fl_meps_det_vdiv_2_5km_calculations
    air_temperature_max_meps_det_vdiv_2_5km_calculations
    air_temperature_min_meps_det_vdiv_2_5km_calculations
    air_temperature_pl_meps_det_vdiv_2_5km_calculations
    air_temperature_z_meps_det_vdiv_2_5km_calculations
    altitude_of_0_degree_isotherm_meps_det_vdiv_2_5km_calculations
    atmosphere_level_of_icing_bottom_hectofeet_meps_det_vdiv_2_5km_calculations
    atmosphere_level_of_icing_top_hectofeet_meps_det_vdiv_2_5km_calculations
    atmosphere_level_of_max_icing_hectofeet_meps_det_vdiv_2_5km_calculations
    bottom_level_of_CAT_hfeet_meps_det_vdiv_2_5km_calculations
    freezing_rain_meps_det_vdiv_2_5km_calculations
    geopotential_height_pl_meps_det_vdiv_2_5km_calculations
    icing_index_max_meps_det_vdiv_2_5km_calculations
    level_of_max_CAT_index_hfeet_meps_det_vdiv_2_5km_calculations
    max_horizontal_wind_shear_meps_det_vdiv_2_5km_calculations
    max_turbulent_kinetic_energy_sqrt_meps_det_vdiv_2_5km_calculations
    max_vertical_wind_shear_meps_det_vdiv_2_5km_calculations
    min_upward_air_velocity_meps_det_vdiv_2_5km_calculations
    precipitation_amount_12h_meps_det_vdiv_2_5km_calculations
    precipitation_amount_1h_meps_det_vdiv_2_5km_calculations
    precipitation_amount_24h_meps_det_vdiv_2_5km_calculations
    precipitation_amount_3h_meps_det_vdiv_2_5km_calculations
    precipitation_amount_6h_meps_det_vdiv_2_5km_calculations
    relative_humidity_2m_meps_det_vdiv_2_5km_calculations
    relative_humidity_pl_meps_det_vdiv_2_5km_calculations
    relative_humidity_z_meps_det_vdiv_2_5km_calculations
    SFX_SST_meps_det_vdiv_2_5km_calculations
    snowfall_amount_12h_meps_det_vdiv_2_5km_calculations
    snowfall_amount_1h_meps_det_vdiv_2_5km_calculations
    snowfall_amount_24h_meps_det_vdiv_2_5km_calculations
    snowfall_amount_3h_meps_det_vdiv_2_5km_calculations
    snowfall_amount_6h_meps_det_vdiv_2_5km_calculations
    specific_humidity_2m_meps_det_vdiv_2_5km_calculations
    specific_humidity_pl_meps_det_vdiv_2_5km_calculations
    SST-T500_meps_det_vdiv_2_5km_calculations
    surface_air_pressure_meps_det_vdiv_2_5km_calculations
    thickness_500_–_1000_meps_det_vdiv_2_5km_calculations
    top_level_of_CAT_hfeet_meps_det_vdiv_2_5km_calculations
    tropopause_air_pressure_meps_det_vdiv_2_5km_calculations
    tropopause_air_temperature_meps_det_vdiv_2_5km_calculations
    undercooled_rain_meps_det_vdiv_2_5km_calculations
    wind_10m_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_10m_speed_meps_det_vdiv_2_5km_calculations
    wind_10m_vector_meps_det_vdiv_2_5km_calculations
    wind_at_maximum_wind_speed_level_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_at_maximum_wind_speed_level_vector_meps_det_vdiv_2_5km_calculations
    wind_fl_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_fl_vector_meps_det_vdiv_2_5km_calculations
    wind_gust_10m_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_gust_10m_vector_meps_det_vdiv_2_5km_calculations
    wind_pl_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_pl_vector_meps_det_vdiv_2_5km_calculations
    wind_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_z_speed_knots_meps_det_vdiv_2_5km_calculations
    wind_z_vector_meps_det_vdiv_2_5km_calculations



#### ec_vdiv_1h

    MS
    air_pressure_at_sea_level_ec_vdiv_1h_calculations
    air_temperature_2m_ec_vdiv_1h_calculations
    air_temperature_pl_ec_vdiv_1h_calculations
    atmosphere_mass_content_of_cloud_liquid_water_ec_vdiv_1h
    atmosphere_mass_content_of_water_vapor_ec_vdiv_1h
    cloud_area_fraction_ec_vdiv_1h
    cloud_area_fraction_pl_ec_vdiv_1h
    cloud_ceiling_ec_vdiv_1h
    dew_point_temperature_2m_ec_vdiv_1h_calculations
    eastward_surface_stress_ec_vdiv_1h
    fog_area_fraction_ec_vdiv_1h
    freezing_level_altitude_ec_vdiv_1h
    geopotential_height_pl_ec_vdiv_1h
    high_type_cloud_area_fraction_ec_vdiv_1h
    integral_of_surface_downwelling_longwave_flux_in_air_wrt_time_ec_vdiv_1h
    integral_of_surface_downwelling_shortwave_flux_in_air_wrt_time_ec_vdiv_1h
    integral_of_surface_net_downward_shortwave_flux_wrt_time_ec_vdiv_1h
    low_type_cloud_area_fraction_ec_vdiv_1h
    lwe_thickness_of_convective_precipitation_amount_acc_ec_vdiv_1h
    lwe_thickness_of_freezing_rain_amount_acc_ec_vdiv_1h
    lwe_thickness_of_snowfall_amount_acc_ec_vdiv_1h
    lwe_thickness_of_stratiform_precipitation_amount_acc_ec_vdiv_1h
    lwe_thickness_of_surface_snow_amount_ec_vdiv_1h
    max_horizontal_wind_shear_ec_vdiv_1h_calculations
    max_vertical_wind_shear_ec_vdiv_1h_calculations
    medium_type_cloud_area_fraction_ec_vdiv_1h
    most_unstable_convective_available_potential_energy_ec_vdiv_1h
    northward_surface_stress_ec_vdiv_1h
    precipitation_amount_1h_ec_vdiv_1h_calculations
    precipitation_amount_acc_ec_vdiv_1h_calculations
    sea_ice_area_fraction_ec_vdiv_1h
    sea_surface_temperature_ec_vdiv_1h_calculations
    sensible_heat_flux_ec_vdiv_1h
    specific_humidity_pl_ec_vdiv_1h_calculations
    SST-T500_ec_vdiv_1h_calculations
    surface_geopotential_ec_vdiv_1h
    surface_temperature_ec_vdiv_1h_calculations
    surface_upward_latent_heat_flux_acc_ec_vdiv_1h
    visibility_in_air_ec_vdiv_1h
    volume_fraction_of_condensed_water_in_soil_sl1_ec_vdiv_1h
    wind_10m_speed_knots_ec_vdiv_1h_calculations
    wind_10m_vector_ec_vdiv_1h_calculations
    wind_pl_speed_ec_vdiv_1h_calculations
    wind_pl_speed_knots_ec_vdiv_1h_calculations
    wind_pl_vector_ec_vdiv_1h_calculations

