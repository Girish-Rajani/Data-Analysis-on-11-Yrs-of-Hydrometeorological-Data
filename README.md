# Data Analysis on 11 Yrs of Hydrometeorological Data

In this project, we are looking at hydrometeorological data from over 30 incomplete datasets spanning 10 years, which includes water, precipitation, snow depth, soil moisture, soil temperature, wind speed/direction, and other factors. Within the scope of this project, the objective is to look for the key features that can 
contribute to snow accumulation.

<img width="896" alt="DPA Project Workflow" src="https://github.com/user-attachments/assets/4897a958-c7db-4036-b7a9-7ae107759c9d">

Before merging all datasets, missing features were replaced with mean/median based on their distribution. During the Exploratory Data Analysis (EDA) phase, bivariate visualization analysis, and correlation plots were created to better understand the relationship between snow accumulation and other factors over a period of time. 

<img width="778" alt="EDA DPA" src="https://github.com/user-attachments/assets/ad56d8ca-f136-4f9c-bb8a-3ea2690aa383">

As shown above, the peak months and years for snow depth (z_s) were observed represented by the top images. It was seen that as the years went on, the overall snow depth increased. The top right visualization shows a negative correlation between snow depth (z_s) and soil temperature (T_g_5) which meant that as the soil temperature increased, the snow depth decreased.

As shown in the second-row images, multicollinearity existed in this dataset, specifically between All the soil temperature features (T_g) and the soil moisture features (s_m). This was handled by merging the features into one soil temperature feature and one soil moisture feature.

<img width="677" alt="DPA Outliers" src="https://github.com/user-attachments/assets/bba1375d-dfe2-43a4-9129-e281cdabc2f9">

Due to the complexity of time series weather data, typical visual inspection failed to detect outliers. Tukey method was successful in visualizing outliers using upper and lower bounds. This method find the indices of the observations in the dataset where the feature is less than the lower bound or greater than the upper bound and then the Winsorize function from the DescTools package was used to deal with outliers. This process is illustrated in the boxplots above. 

<img width="695" alt="PCA DPA" src="https://github.com/user-attachments/assets/0574f1a6-1387-41cb-9c11-cc50dbc9b85d">

Finally, principal component analysis (PCA) was performed to identify the most significant features within the large dataset that affect snow accumulation. A PCA Biplot was create on the left image as shown above. We observe that positively correlated variables are grouped together and negatively correlated variables are located on opposite sides of the plot origin.

In conclusion, it was observed that:

- Features such as relative humidity (RH), Wind Corrected Precipitation (ppt_a), and fraction of precipitation that is snow (perc_snow) are all positively correlated to snow depth (z_s).
- However, features such as Air Temperature (T_a), Dew Point Temperature (T_d), and Water Vapor Pressure (e_a) are negatively correlated to snow depth (z_s).
- Lastly, features such as Soil Temperatures (T_g) and Soil Moistures (s_m) are not likely to be correlated to snow depth (z_s) since they meet at 90 degree angle.


