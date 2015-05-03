## Mean Shift Clustering
MeanShift_py is a simple implementation of [mean shift](http://en.wikipedia.org/wiki/Mean_shift) clustering in python.

### Dependencies
The only dependency is [Numpy](http://www.numpy.org/)

### Description
The `mean_shift_python.py` module defines a class called `MeanShift`. The `MeanShift` class constructor takes in an optional kernel parameter. If no kernel is specified, a default [Gaussian](http://en.wikipedia.org/wiki/Gaussian_function) kernel is used.

The `cluster` method requires an array of points and a kernel bandwidth value. A optional `iteration_callback` function can also be passed in that will be called back at the end of each mean shift iteration with the current state of the algorithm (e.g., where the points are currently at, along with an iteration number).

After the clustering finishes, a `MeanShiftResult` object is returned, containing three arrays:

1. The original points
2. The shifted points
3. Cluster assignments for each point

### Usage
```python
import mean_shift_python as ms

data = get_data_from_somewhere()
mean_shifter = ms.MeanShift()
mean_shift_result = mean_shifter.cluster(data, kernel_bandwidth = 10)

original_points =  mean_shift_result.original_points
shifted_points = mean_shift_result.shifted_points
cluster_assignments = mean_shift_result.cluster_ids
```
