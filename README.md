## Parallel post-processing for Vehicle Routing Problem (VRP)

Vehicle Routing Problem (VRP) is a NP-hard problem. There are many heuristics to solve VRP problem that provides near-optimal solution. 

However, solving the VRP is not always the end. Sometimes we need to do some post-processing on the routes, for example: in collaborative routing problem, one issue is to distribute the cost of the tour among the participants in a fair manner. It turns out that this issue of fairness can be solved using a linear program for each of the route produced by the initial VRP solution. However, depending on the problem, we might have numerous routes to solve for and doing it sequentially could be time consuming. Since the routes are independent of each other, this provides us with a perfect opportunity to parallelize the problem. 

In this project, we consider solving a VRP that has around 400 individual nodes and the initial heuristic produces approximately 151 routes (the initial heuristic is not provided here, only the routes produced by the heuristic are provided in a .pkl file, this file acts as the input for the main.py program). We consider doing the post-processing step for these 151 routes in parallel distributed among multiple processors.