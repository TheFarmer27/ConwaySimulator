# Conway's Game of Life Simulator

*This project is taken from the book "Python Playground" by Mahesh Venkitachalam.*

Conway.py replicates Conway's Game of Life.

## Imports ##

We import the sys and argparse to be able to run the program from the command line. We then import numpy as np. We then import matplotlib twice, once using pyplot as plt, and the ohter using animation as animation.

Reading the code from top to bottom, after the imports, we define the values of 'ON' and 'OFF' as colors using rgb notation. The colors are used in the 'addGlider' function. The values are used in the 'update' function, specifically when implimenting conway's rules.

## Functions ##

Then four global functions are used.

### randomGrid ###

In the 'randomGrid' function, we use the parameter 'N', which is defines how long each side of the grid will be. When the function is called, it will return the , the size of the gameboard, the probabilities of the values of "ON" and "OFF" respectively. Then the grid is shaped to be the size of NxN.

 ### addGlider ###

In the 'addGlider' function, we use the parameters of 'i', 'j', and 'grid'. 'i' represent the x-axis of the board, and 'j' represents the y-axis. The glider itself is the observed pattern that move across the grid. Glider is defined as a numpy array with each cell having the value of "ON" or "OFF". The grid is defined as an array with the possible values of the neighboring cells.

### Update ###

In the 'update' function, we using the parameters of frameNum, img, grid, and N. We use ranges for each of 'N' in 'i' and 'j' parameters to compute the value of the eight individual neighboring cells. We divide the array by N and take the remainder as whether to set 'j' back to zero or not. Here we apply the rules of the game.

### Main ###

When calling the 'main' function, we use the class 'argparse' to be allowed to add arguments. The arguments in particullar are 'grid-size', 'mov-file', 'interval', 'glider'. All values are stored in the variable args.

After the arguments, we set both the grid size and the interval of when the value changes. We then declare the grid as a numpy array. After this, we check if the 'glider' parameter is specified from the command line. 

We then set up the animation for the change of cell apperance according to the cell. 
The img variable stores the values 'grid' and 'interpolation', which is defined with the string 'nearest', telling the program to check the value of the cells closest to a specific cell. We then show the grid for Conway's Game of Life.

Finally, we check if the function is called from the command line.