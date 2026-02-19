# dynamic-maze

Task

The task involves programming an autonomous robot to navigate around a series of different mazes, with the goal of being able to route back and forth through the maze via the fastest route possible.

Objectives:
-Detect the red tile marking the end of the maze
-Escape the maze via the fastest route
-Return home via the fastest route

My program solves this task using the left-turn rule, in which the robot will always attempt to turn left when it has the opportunity to do so. If it cannot turn left, it will attempt to go straight, and if that is not possible, it will turn right. By repeating this process, the robot is guaranteed to eventually reach the red tile, which is detected using the eye sensor.

To ensure my robot takes the fastest path, the program records the coordinates (x/y) of the robot every time a successful movement is made. These are stored in an ordered list showing the progression of the robot through the maze.

To make sure the robot takes the fastest route to and from the start, I have added a trimming loop. After each coordinate has been entered, the program checks to see whether it has been entered previously. If a coordinate has been entered before, this implies there is an unnecessary loop in the path. The program will then remove that location and any previous ones within that loop.

Once the robot has reached the red tile, it will begin its journey back but will need to know which direction to face. This is solved using the atan2 function, which calculates the displacement vector in relation to the next coordinate required. The robot will then turn to face that direction and drive forward. This process is repeated until it reaches the starting square.

References

https://api.vex.com/vr/home/playgrounds/dynamic_wall_maze.html
https://en.wikipedia.org/wiki/Shortest_path_problem
https://docs.python.org/3/library/math.html#math.atan2
https://education.vex.com/stemlabs/vr/vr-activity-labs






