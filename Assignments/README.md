# HW2 Anomaly Event Detection
Project for datamining homework 2. Implements a sliding window threshold calculation to determine anomalies in a time-series dataset. Implemented via jupyter notebook file.

## Requirements

numpy & pandas

Both of these can be easily installed via command line using pip (pip3 if python3).

-Optional- 

matplotlib.pyplot

This is only necessary for plotting results at the end, if you do not wish to plot your results you can comment this import out.

jupyter (or alternative)

Since this program is delivered via ipynb you must have something that can run this file type, normally jupyter is used for this matter but you can choose whatever you like.

## Usage

The first two cells perform the necessary imports and prepares the dataframe, ensure that you have the file 'AG_NO3_fill_cells_remove_NAN.csv' in the same directory as the ipynb file. Note that the window size and percentile are set in the second cell, these can be adjusted however you see fit as long as 100 > q > 0 and window > 0.

The third cell labels the first window of data points by calculating the window threshold, and then comparing each datapoint in the window against it.

The fourth cell walks through the data, first moving the window by 1 step, then calculating the new threshold, and lastly checking the new datapoint in the window against the new threshold. 

The fifth cell then checks the dataset and reports the numbers of: Anomalies Detected, True Normal Events in the dataset, Student Flags, True positives, and False positives. It also calculates the following: Correct Anomaly Detection Rate, and Correct Normal Event Detection Rate.

The last cell performs the plotting of the results, ensure you have matplotlib.pyplot imported to run this cell.

## Discussion

This was a rather brute force way to attempt anomaly detection. Originally our code checked and updated every data point in the window at each step. This led to very poor performance time-wise and detection wise. Perhaps we were overfitting the data in this approach. In our final approach it checks every data point only once. This led to much better performance time-wise but may have led to underfitting in our detection.

## Results

Below is our output for the program when run with a window size of 100 and a threshold of 98.

![Results](Screenshot.png)

As you can see the False Positive number is rather high although our detection rates fall within the specified limits for this project. Futher tuning is needed before this should be implemented however.

Below is our plotted results. Green points indicate true positives and red points indicate false positives.

![Plot](Screenshot_2.png)




