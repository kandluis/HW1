
# CS 182: Artificial Intelligence
# Assignment 1: Search Algorithms
* Fall 2015
* Due: **updated** September 21, 11:59pm

In this assignment, you will implement search algorithms to help Pacman find paths in a maze. 
Note: We will use the Pacman framework developed at Berkeley. This framework is used worldwide to teach AI, therefore it is very important that you DO NOT publish your solutions online.





![Pacman](https://upload.wikimedia.org/wikipedia/en/5/59/Pac-man.png)



## Computational Assignment

### Question 1

Follow the instructions at:

http://ai.berkeley.edu/search.html

The page includes questions requiring implementation of some of the search algorithms we studied in class. [The grading scheme described on the Berkley webpage will not be used, but can be used for your own testing for evaluating your performance.]

To get the assignment we recommend just cloning this repo:

> git clone https://github.com/CS182/HW1.git

 Solutions should be submitted to the course dropbox folder. Submit only the files `search.py` and `searchAgents.py`. If you work in a pair, only one student should submit the files, but make sure to include the names of both students at the top of each of the files.


### Important Note:

There is an optimization to graph search that we did not cover in class that will help with the homework.

For BFS and DFS you can avoid pushing paths that are already on the frontier. This is valid because for these algorithms, paths of the same depth and last state are equivalent. You can however _not_ do this for UCS or A\* since these algorithms are aware of the path cost, and so it is possible that, from the algorithms perspective, the new path is superior to a path with the same last state that was previously added to the frontier. 

In practice, you can implement this by special casing BFS and DFS to add a state to the explored list _when_ it is  pushed on the frontier (as opposed to when it is popped). This will make BFS (in particular the medium corners problem on the HW) much faster. However if you implement it as in the notes we will not take off points.

Furthermore, in AIMA they also note that for BFS you can accept a solution path on pushing as opposed to on exploring (popping). Implementing this will give you a small speed up on this problem, but potentially a larger speed-up on problems with a large branching factor. In our implementation, BFS requires 1966 expansions after the first change, 1921 after the second, and several minutes without either change. 

## Written Assignment 

Answer the following questions individually, and submit as pdf to the dropbox folder. 

### Question 1

The Pac-Man board will show an overlay of the states explored and the order in which they were explored. (Brighter red means earlier exploration.) Is the exploration order the one you would have expected? Does Pac-Man actually go to all the explored squares on his way to the goal? (Question 1 on the Berkeley search project page.)


### Question 2

 With regards to question 4 in the implementation of A\* as specified by question 4 on the Berkeley search project page: Run the A\* agent on openMaze. How do A\* and UCS perform with this configuration?


### Question 3

Describe a real world problem for which you would want to find an optimal solution. Briefly explain why (3-4 sentences). 


### Question 4

Describe a real-world problem for which you would prefer finding a solution quickly, even if it is suboptimal. Briefly explain why (3-4 sentences). 

