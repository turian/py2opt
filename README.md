[![license](https://img.shields.io/github/license/DAVFoundation/captain-n3m0.svg?style=flat-square)](https://github.com/DAVFoundation/captain-n3m0/blob/master/LICENSE)

# 2-Opt Search Algorithm 

In optimization, 2-opt is a simple local search algorithm with special swapping mechanism that suits well to solve the 
traveling salesman problem. This algorithm is sensitive to the initial point of search, i.e., its final results get 
changed by different initial points. 2-opt runs very fast such that a tsp with 120 cities can be solved in less than 
5 sec on the intel core i7. To get a more reliable result, you should run the 2-opt with different randomized initial 
points for enough number of times. One more thing, the travelling salesman problem has many applications in real world 
such as logistic planning or DNA sequencing. So, having a fast and simple method to solve the TSP is valuable. 

 
## Library
The library requires the following libraries:

* numpy
* random2

## Install

It can be installed using pip:
```python
pip install py2opt
```

## Usage

To use this library, you must have a distance matrix showing the pair distance among all nodes. Then, the first thing 
to do is create an instance of the RouteFinder class. 

```python
from py2opt.routefinder import RouteFinder

nodes = ['A', 'B', 'C', 'D']
dist_mat = [[0, 29, 15, 35], [29, 0, 57, 42], [15, 57, 0, 61], [35, 42, 61, 0]]
route_finder = RouteFinder(dist_mat, nodes, iterations=5)
best_distance, best_route = route_finder.solve()

print(best_distance)
114
print(best_route)
['A', 'C', 'B', 'D']
```
The solver finds out the optimum order (re: minimum total distance traveled) in which the nodes must be visited along 
with the total distance traveled. Note that the 2-opt algorithm doesn't guarantee the global optimum similar to other 
heuristic search algorithms. So, the results can vary in each iteration.


And that's pretty much it!

