# Vaex
## Using Fast loading libraries like Vaex

Vaex is a high-performance Python library for lazy Out-of-Core DataFrames (similar to Pandas), to visualize and explore big tabular datasets. 

It calculates statistics such as mean, sum, count, standard deviation, etc, on an N-dimensional grid for more than a billion (10^9) samples/rows per second. 

Visualization is done using histograms, density plots, and 3d volume rendering, allowing interactive exploration of big data.

Vaex uses memory mapping, zero memory copy policy, and lazy computations for best performance (no memory wasted).

Now, we will implement the vaex library in the randomly generated dataset to observe the performance.

## Step 1: import a vaex library

import vaex

## Step 2: we need to convert the CSV file to the hdf5 file using the vaex library. 

#converting csv to hdf5 format
df=vaex.from_csv('dataset_vaex.csv',convert=True)

After executing the above code, a dataset_vaex.csv.hdf5 file is generated in your working directory. 

It is observed that it took less time to convert CSV to hdf5 file which is less time relative to the size of the file.

## Step 3. Reading hdf5 file using vaex.

Now we need to open hdf5 file by open function in the vaex library.

%%time
#opening hdf5 file
df_vaex=vaex.open('dataset_vaex.csv.hdf5')
print(df_vaex.head())

After observing the above code if we see the output, it looks like it took less time to read an hdf5 file by this we can understand how fast it is executed to read a 3GB hdf5 file. This is the actual advantage of the vaex library.

## By using vaex we can be able to perform different operations on the large data frames like-

•	Expression System
•	Out of core data frame
•	Fast groupby / aggregations
•	Fast and efficient join

## Why vaex

•	Performance: works with huge tabular data, processes rows/second

•	Lazy / Virtual columns: compute on the fly, without wasting ram

•	Memory efficient: no memory copies when doing filtering/selections/subsets.

•	Visualization: directly supported, a one-liner is often enough.

•	User friendly API: you will only need to deal with the DataFrame object, and tab completion + docstring will help you out: ds.mean<tab>, feels very similar to Pandas.

•	Lean: separated into multiple packages

•	Jupyter integration: vaex-jupyter will give you interactive visualization and selection in the Jupyter notebook and Jupyter lab.
