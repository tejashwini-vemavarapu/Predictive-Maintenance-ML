# Predictive-Machinery-Analysis-ML
# Problem Setting: 
Today, all businesses depend on machines, and we want them to work at their best for a long period. In most cases, Predictive maintenance can be used to maximize the efficiency of machinery. It helps to minimize unanticipated breakdowns as we can fix the machines just in time as we monitor and predict their status. Here, the problem is defined within the context of a manufacturing process, where the machine used in the process can fail due to various reasons. The goal is to understand the factors that contribute to machine failure and to predict when it is likely to occur.

# Problem Definition: 
The specific problem being addressed is to identify the factors that contribute to machine failure and to predict when it is likely to occur. The following questions need to be answered through data analytics:

•	What are the factors that contribute to machine failure?

•	How can we predict when a machine is likely to fail?

•	Which failure mode is the most likely to occur?

# Data Sources: 
Stephan Matzka, School of Engineering - Technology and Life, Hochschule fÃ¼r Technik und Wirtschaft Berlin, 12459 Berlin, Germany, stephan.matzka '@' htw-berlin.de
https://archive.ics.uci.edu/ml/datasets/AI4I+2020+Predictive+Maintenance+Dataset#


# Data Description: 
The dataset consists of 10,000 data points stored as rows with 14 features in columns. 
The variables include:
•	UID: unique identifier ranging from 1 to 10,000

•	product ID: consisting of a letter L, M, or H for low (50% of all products), medium (30%) and high (20%) as product quality variants and a variant-specific serial number

•	air temperature [K]: generated using a random walk process later normalized to a standard deviation of 2 K around 300 K

•	process temperature [K]: generated using a random walk process normalized to a standard deviation of 1 K, added to the air temperature plus 10 K.

•	rotational speed [rpm]: calculated from a power of 2860 W, overlaid with a normally distributed noise

•	torque [Nm]: torque values are normally distributed around 40 Nm with a Ïƒ = 10 Nm and no negative values.

•	tool wear [min]: The quality variants H/M/L add 5/3/2 minutes of tool wear to the used tool in the process.

•	'machine failure' label: indicates whether the machine has failed in this particular datapoint.

# The machine failure consists of five independent failure modes:
•	tool wear failure (TWF): the tool will be replaced of fail at a randomly selected tool wear time between 200 – 240 mins (120 times in our dataset).
  At this point in time, the tool is replaced 69 times, and fails 51 times (randomly assigned).

•	heat dissipation failure (HDF): heat dissipation causes a process failure, if the difference between air- and process temperature is below 8.6 K and the tool’s rotational speed is below 1380 rpm. This is the case for 115 data points.

•	power failure (PWF): the product of torque and rotational speed (in rad/s) equals the power required for the process. If this power is below 3500 W or above 9000 W, the process fails, which is the case 95 times in our dataset.

•	overstrain failure (OSF): if the product of tool wear and torque exceeds 11,000 minNm for the L product variant (12,000 M, 13,000 H), the process fails due to overstrain. This is true for 98 datapoints.

•	random failures (RNF): each process has a chance of 0,1 % to fail regardless of its process parameters. This is the case for only 5 datapoints, less than could be expected for 10,000 datapoints in our dataset.

If at least one of the above failure modes is true, the process fails and the 'machine failure' label is set to 1. It is therefore not transparent to the machine learning method, which of the failure modes has caused the process to fail.
