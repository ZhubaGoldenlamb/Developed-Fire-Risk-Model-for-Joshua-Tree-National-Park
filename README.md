# Developed Fire Risk Model for Joshua Tree National Park  
### Analyzing desert fire trends using open-source 10 m Sentinel-2 NDVI time series  

My workflow offers land managers a repeatable method to monitor fine-fuel accumulation and detect high-risk fire conditions in arid landscapes.

---

## **Overview**

Wildfires in Joshua Tree National Park have increased with the spread of invasive annual grasses such as **Red Brome**, **Cheatgrass**, and **Split Grass**. These grasses form continuous fine-fuel beds that persist on the landscape for years, allowing fire to carry through otherwise sparse desert vegetation.

This project analyzes five years of **Sentinel-2 NDVI data (2019–2023)** to identify vegetation stress patterns that preceded the **2022 Elk Fire**.

---

## **Key Goals**

- **Quantify conditions that create peak wildfire risk** in Joshua Tree National Park so land managers can identify high-risk years and justify funding for fuel breaks and proactive mitigation.  
- **Advance understanding of desert fire ecology** by documenting how wet-year biomass growth followed by multi-year drying (“curing”) creates the highest potential for fire spread.

---

## **Methods**

To monitor vegetation conditions leading up to the 2022 Elk Fire, I analyzed time-series **Sentinel-2 satellite imagery** using **ArcGIS Pro**. Sentinel-2 imagery was selected because it provides **open-source 10 m spatial resolution data**, which is fine enough to capture vegetation changes in desert environments without requiring costly aerial imagery.

All satellite imagery was downloaded from the **Copernicus Data Hub**, which provides free public access to Sentinel-2 data from the European Space Agency. I selected cloud-free Sentinel-2 images from **late March** for each year between **2019 and 2023**, aligning image acquisition dates with the end of the invasive grass growing season.

For each image, I calculated the **Normalized Difference Vegetation Index (NDVI)** using the red (Band 4) and near-infrared (Band 8) bands, which are sensitive to vegetation greenness and biomass. NDVI rasters were generated in ArcGIS Pro using the **Raster Calculator** tool.

Using a polygon of the **Elk Fire burn scar**, I summarized vegetation conditions within the burned area using the **Zonal Statistics** tool to extract mean NDVI values for each year. These values were compiled into a table and graphed to visualize vegetation trends over time. NDVI trends were then compared with annual precipitation data from a nearby NOAA weather station to interpret how wet years followed by multi-year drying influenced fuel conditions prior to the fire.

### **Workflow Overview**
![NDVI workflow diagram](Elk_NDVI_Workflow_Official.png)

*Workflow diagram showing the process of downloading Sentinel-2 imagery, calculating NDVI using red and near-infrared bands, and extracting mean NDVI values within the 2022 Elk Fire burn scar using zonal statistics.*

---

## **Results**

### **Vegetation Greenness Trends (NDVI)**

To understand how vegetation conditions changed before the 2022 Elk Fire, I analyzed mean **Normalized Difference Vegetation Index (NDVI)** values within the Elk Fire burn scar from **2019–2023**. NDVI values range from 0 to 1, with higher values indicating greener and more abundant vegetation.

The results show a clear decline in vegetation greenness leading up to the fire. NDVI values were highest in **spring 2019**, following a wet year that promoted strong growth of invasive annual grasses that persist on the landscape for multiple years. From **2020 through 2022**, NDVI steadily declined, indicating that shrubs were drying and curing over multiple years. The Elk Fire occurred in **late May 2022**, after three consecutive years of low NDVI values, suggesting that fuels were both abundant and dry at the time of ignition.

![Mean NDVI values (2019–2023) within the Elk Fire burn scar](elk_fire_2022_mean_ndvi.png)

*Mean NDVI values calculated from late-March Sentinel-2 imagery (2019–2023) within the Elk Fire burn scar. NDVI values declined by approximately 47% between 2019 and 2022, indicating progressive drying of vegetation prior to the fire.*

---

### **Precipitation Patterns and Context**

Annual precipitation data from a nearby NOAA weather station helps explain the observed NDVI trends. Rainfall was highest in **2019**, corresponding with the peak NDVI values observed that spring. Precipitation then declined in **2020, 2021, and 2022**, contributing to prolonged drying of both invasive grasses and native shrubs across the landscape.

Although **2023 experienced unusually high rainfall**, NDVI values within the Elk Fire scar did not immediately rebound to pre-fire levels. This is likely because the fire removed much of the existing vegetation, and early regrowth is dominated by invasive annual grasses rather than mature shrubs or Joshua trees.

![Annual precipitation totals near the Elk Fire site (2019–2023)](Elk_Fire_2019_2023_Precipitation_Histogram.png)

*Annual precipitation totals from a NOAA weather station near the Elk Fire site (2019–2023), showing a wet year followed by multiple dry years preceding the 2022 fire.*

---

### **Key Quantitative Finding**

Using open-source **10 m Sentinel-2 imagery**, this analysis detected a **47% decline in NDVI values between 2019 and 2022** within the burned area. Despite the relatively coarse resolution compared to sub-meter imagery, the workflow successfully captured meaningful vegetation trends in a sparse desert environment.

---

## **Conclusion**

This project demonstrates that wildfire risk in Joshua Tree National Park is highest **not immediately after wet years**, but after **multiple years of drying that follow strong vegetation growth**. Wet winters promote the spread of invasive annual grasses, while subsequent drought years allow those grasses — along with native shrubs — to cure and persist as fine fuels.

By using freely available **Sentinel-2 imagery** and a repeatable NDVI workflow, land managers can monitor fuel conditions over time and identify periods when wildfire risk is elevated. A sustained decline in NDVI following a high-growth year may serve as an early warning signal that proactive mitigation — such as fuel breaks, fire patrols, or targeted management — is needed.

Importantly, this workflow provides a **cost-effective and scalable tool** for desert fire monitoring, helping managers allocate limited resources more strategically while protecting one of the most vulnerable ecosystems in the Mojave Desert.
