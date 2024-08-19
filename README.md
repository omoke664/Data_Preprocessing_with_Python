# Outlier Detection in Diabetes Pedigree Function Data (Python)

This project demonstrates how to identify and remove outliers from a dataset focusing on the 'DiabetesPedigreeFunction' feature. It utilizes Python's NumPy library for efficient calculations.

## Installation

If you haven't already, install the required library:
Load your data:

Replace clean_data with your actual DataFrame containing the 'DiabetesPedigreeFunction' column.
Identify quartiles:
Replace clean_data with your actual DataFrame containing the 'DiabetesPedigreeFunction' column.

q1, q3 = np.percentile(clean_data['DiabetesPedigreeFunction'], [25, 75])


Calculate interquartile range (IQR):
iqr = q3 - q1


Calculate lower and upper bounds:

lower_bound = q1 - (1.5 * iqr)
upper_bound = q3 + (1.5 * iqr)


Filter data (remove outliers):


clean_data = clean_data[(clean_data['DiabetesPedigreeFunction'] >= lower_bound) & (clean_data['DiabetesPedigreeFunction'] <= upper_bound)]


(Optional) Analyze and visualize the filtered data:

Perform further analysis on the filtered clean_data to explore its characteristics.
Consider using libraries like Matplotlib or Seaborn to create visualizations.



This script implements the Interquartile Range (IQR) method to detect outliers in the 'DiabetesPedigreeFunction' feature of your dataset. Here's a breakdown of the steps:

NumPy percentile: Calculates the first quartile (Q1) and third quartile (Q3) of the data, representing the 25th and 75th percentiles, respectively.
IQR: The IQR is the difference between Q3 and Q1, representing the range within which most of the data falls.
Bounds: Lower and upper bounds are calculated by subtracting/adding 1.5 times the IQR from Q1 and Q3, respectively. These bounds define the expected range of "normal" values.
Filtering: Data points outside the lower and upper bounds are considered outliers and filtered out, resulting in a dataset with reduced outlier influence.
Additional Notes
The IQR method is a common approach for outlier detection, but other methods (e.g., Z-score) might be more suitable depending on your data distribution.
The choice of the IQR multiplier (1.5) can be adjusted based on the expected level of outlier presence in your data.
Consider exploring further data analysis and visualizations to gain deeper insights into the filtered dataset.
