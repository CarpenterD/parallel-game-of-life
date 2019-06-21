# Parallelisation of the *Game of Life*

This 'c' program simulates [The Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life#Variations), using
[OpenMP](https://www.openmp.org/) multi-threading to accelerate generation calculations.

This project was undertaken in 2018 as an assignment for *CITS3402: High Performance Computing*
\([website](http://teaching.csse.uwa.edu.au/units/CITS3402/)/[description](http://handbooks.uwa.edu.au/unitdetails?code=CITS3402)\) at The University of Western Australia.
The written report is included for completeness, take its conclusions and analysis with a grain of salt.

### Usage

Compiling with `gcc`:
```
$ gcc -std=c99 -fopenmp -o gofl gofl.c
```

Run code in one of the following ways:
- `./gofl <size> <generations>` to simulate a randomly generated board with all available threads
- `./gofl <size> <generations> <threads>` to simulate a randomly generated board with a specified number of threads
- `./gofl <size> <generations> <threads> <infile>` to load and simulate and existing board with a specified number of threads

*Note that all boards are square in size.*

##### Parameters

- `size`: the size of the square board. If size = n, the board with contain n*n tiles
- `generations`: the number of successive generations to simulate. '0' will return the original state of the board
- `threads`: the number of threads to utilise
- `infile`: location of file containing initial board configuration. Values should
be separated by a single space, with each row on a new line. '0' and '1' represent dead and alive cells respectively

### Learning HPC?

Since parallelising the Game of Life is a fairly common educational exercise,
feel free to first _*learn*_ from the code and only then use it if you need (don't
forget to reference!).

I also highly recommend the videos in [Tim Mattson's tutorial series](https://www.youtube.com/watch?v=nE-xN4Bf8XI).
