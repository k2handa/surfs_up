# Surfs_UP Challenge 

## Overview of Project

### Purpose

 * The purpose of this analysis is to compare the weather data between June and Decemeber using the hawaii sqlite data. This is important to the client since they are looking to invest in a surf and ice cream shop. knowing the fluctuation in the temperature data will give the client the necessary information to make a informed decision whether the shop will be sustainable all year round. 


## Results

 * Average Temperature 
		-  Between the 2 months, we can see that the avg temperature for June is around 75 degrees, while in December it is 71. we can see there is about a 4 degree drop off between the 2 months the client is looking at. 

 * Difference in Min and Max 
	   	- Although the max temperatures between the 2 months are farely close (june = 85, december = 83) the min temperatures differe greatly. The minimum temperature however has much more of a discrepency. June sat at 64 while december at 56, a much higher difference on the minimum point. at these temps there wouldnt be much surfing or ice cream sales. 


### Summary

	* From our analysis we can see that the month of December is a cooler month, and will have more days where the durf ice cream shop will not be profitable because of the lower tempaeratures. Beyond the Temperatures we were asked to get for the months of June and December, additional data that would prove relevant would be precipatation and the weather stations gathering the data. 

	* while temperature is important for a surf and ice cream shop, precipatation can also affect the businesses success. having wetter rainier days will reduce traffic to the shop. knowing how much precipitation and the average precipation will give context to how the months sales will play out. the query will just add Measurements.prcp to the code 'session.query(Measurement.tobs, Measurement.prcp).filter(extract('month', Measurement.date) == 12)' and the same for june 'session.query(Measurement.tobs, Measurement.prcp).filter(extract('month', Measurement.date) == 6)'. this will add the precipitation numbers for the 2 months we are looking at. 

	* another important factor to look at is the data gathering stations themselves. some stations may gather more data than other, or have better gathering techniques then others and should be considered more when piecing together our data and results. first you would need to determine how many stations there were and and which ones are the most reliable. 'session.query(Measurement.station, func.count(Measurement.station)).\
	group_by(Measurement.station).order_by(func.count(Measurement.station).desc()).all()'
	then from here add in your temperatures and your precipitations to see what the reading is for the specific station you are looking into. 