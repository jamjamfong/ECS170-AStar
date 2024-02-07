# ECS170-AStar

PROJECT DESCRIPTION

This is a project for ECS170 Introduction to Artificial Intelligence. Starter code was given, and my code begins in module 2.2. Here, I implement three different heuristics into Dijkstra's algorithm to find the optimal path between two points accross a map with varying terrain. Explanations for each heuristic can be found below. 


EXPONENTIAL HEURISTIC

My heuristic utilizes Chebyshev distance with an elevation penalty aligned with the cost function.To prove admissibility, we must prove that it does not overestimate and it is consistent. To start, Chebyshev distance itself is an admissible heuristic. The penalty is defined as the e constant,  ensuring consistency. It is also a non-negative term. This means that it will never produce a heuristic value that is non-negative. Therefore, the heuristic does not overestimate and is admissible. 


DIVISION HEURISTIC

For the division cost function, I followed similar steps. It is another variation of Chebyshev distance with a penalty implementation. Again, Chebyshev distance itself is an admissible heuristic. We can prove that it is always nonnegative by evaluating the penalty. Looking at the equation, the penalty will always be greater than or equal  to 1. Therefore, it will never overestimate the path cost. Next, we must prove that it is consistent. In this case, the penalty has direct influence by the height change. 
Because of this relationship, the penalty term does not have a large increase in comparison to the increase in distance. Thus, it is consistent to a reasonable degree. 


ASTAR WEIGHTED

In general, I followed the same approach for the A* variant as I did for the exponential cost function heuristic. However, I added a weight factor to fine-tune the algorithm’s behavior. The two weight factors are defined as the variables g_weight and h_weight and are located in the loop which evaluates neighboring nodes. These variables place weight on the movement cost. A higher g_weight value will emphasize actual path costs, which can find shorter but more expensive paths. A higher h_weight prioritizes heuristic guidance, which can find cheaper but longer paths. In comparison to regular A*, weighted A* allows for calibration between optimality and efficiency. Although, I found that it was very difficult to find the sweet spot for the weighted values. Being only slightly off can increase the path cost, time, and nodes explored by quite a lot. After tweaking the values many times, I found that setting them both at 0.4 will produce the best results. Weighted A* can also increase performance. 
