# Solar Power in India
In this case study a data analysis has been performed on data concerning solar power generation.
The data has been gathered at a solar power plant in India over a 34 day period. There is one power generation dataset and one sensor readings dataset. 
The power generation datasets are gathered at the inverter level - each inverter has multiple lines of solar panels attached to it. 
The sensor data is gathered at a plant level - single array of sensors optimally placed at the plant.  
  
In this research the following questions were answered:  
**Can we predict the power generation for next couple of days?    
Can we identify the need for panel cleaning/maintenance?  
Can we identify faulty or suboptimally performing equipment?**  

## Insights Summary

**Several types of malfunctions have been found within these plants.**  
Generator data:   
- AC_power values are around 10 times less than DC-power, while it should be around the same.
- 26.5 hours of missing time stamps. There are no values present during this time.
![image](https://github.com/user-attachments/assets/9a87ddae-1eea-4dca-8c80-88743d8bf9e9)

- Time stamps with missing inverter records.
- These inverters records were usually missing within the same inverter groups. These are probably connected and maintenance needs to be carried out here. 
- Inverter 'bvBOhCH3iADSZry' and '1BY6WEcLGh8j5v7' generated significantly less power than others, respectively 87.59% and 88.94% compared to the most producing inverter. Maintenance needs to be carried out here.


![image](https://github.com/user-attachments/assets/a5ccbb6e-ec7a-4dc8-bccc-cf4b4045ed1f)


Weather data:
- 0.85 hours of missing time stamps. There are no values present during this time.
  ![image](https://github.com/user-attachments/assets/8f17ca2c-a695-4137-b811-5a69ed4360b1)

  
**Other findings:**  

Generator/Weather data:  
- The strongest predictor for ac/dc power is the irradiaton. However, ac_power and dc_power are also strongly correlated with the ambient temperature with a correlation of 0.72. One could therefore use the weather prediction to predict the output of the inverters.

![image](https://github.com/user-attachments/assets/fb342374-ddbb-428e-a9d5-923f1bde3a79)

- Irradiation of one day is a reasonably strong predictor for the next day, but not for days after that. 

## Recommendations. 
**Can we predict the power generation for next couple of days?**   
Yes, this is possible, there is a correlation of 0.72 between ac/dc power and ambient temperature. This is a strong positive correlation, indicating that if one increases, the other one tends to increase as well. The real cause of ac/dc power is irradiation, however temperature seems to be a relative good proxy for this. By following the weather forecase one could predict the ac/dc power for the coming days.  


**Can we identify the need for panel cleaning/maintenance?**  
Inverter 'bvBOhCH3iADSZry' and '1BY6WEcLGh8j5v7' generated significantly less power than others, respectively 87.59% and 88.94% compared to the most producing inverter. There is a good chance there is cleaning or maintenance needed to fix this.


**Can we identify faulty or suboptimally performing equipment?**  
The mean and max of ac_power is almost 10 times as low as dc_power. This unexpected, since it is expected to be around the same value. This could indicate a malfunctioning of the system.   
  
Also, in the generation data 32.896 of the 34 days have been recorded, missing over one day of values. This indicates something malfunctioning within the equipment. 
The biggest gaps were:  
   
From 2020-05-20 13:30 to 2020-05-20 17:15 = 3 hours 4 5 minutes  
  
From 2020-05-20 23:00 to 2020-05-21 07:30 = 8 hours 30 minutes  
  
From 2020-05-28 22:30 to 2020-05-29 06:00 = 7 hours 30 minutes  
  

Of the time stamps which were recorded, 96.8% of the time stamps have observations of all the 22 inverters, while 3.2% have less than 22 observations. There were often a combinations of inverters observations missing. See below for more details about which inverters were often missing together.
  
  
In the weather data 0.85 of 34 days of values were missing. 
  
Biggest time gaps:  
  
2020-05-20 13:30:00 to 2020-05-20 17:15:00 = 3 hours 45 minutes  
  
2020-05-21 00:45:00 to 2020-05-21 07:30:00 = 6 hours 45 minutes  
  
2020-05-29 02:00:00 to 2020-05-29 06:00:00 = 4 hours 0 minutes  
