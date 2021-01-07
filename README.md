# Computer Systems A Coursework: Game of Life Simulation

This project was completed as coursework for a University module in my second year. We worked on the task in pairs and coordinated work online via Discord due to COVID-19.

## Task Description

The British mathematician John Horton Conway devised a cellular automaton named ‘The Game of Life’. The game resides on a 2-valued 2D matrix, i.e. a binary image, where the cells can either be ‘alive’ (pixel value 255 - white) or ‘dead’ (pixel value 0 - black). The game evolution is determined by its initial state and requires no further input. Every cell interacts with its eight neighbour pixels: cells that are horizontally, vertically, or diagonally adjacent. At each matrix update in time the following transitions may occur to create the next evolution of the domain:

- any live cell with fewer than two live neighbours dies
- any live cell with two or three live neighbours is unaffected
- any live cell with more than three live neighbours dies
- any dead cell with exactly three live neighbours becomes alive

Consider the image to be on a closed domain (pixels on the top row are connected to pixels at the bottom row, pixels on the right are connected to pixels on the left and vice versa). A user can only interact with the Game of Life by creating an initial configuration and observing how it evolves. Note that evolving such complex, deterministic systems is an important application of scientific computing, often making use of parallel architectures and concurrent programs running on large computing farms.

Your task is to design and implement programs which simulate the Game of Life on an image matrix.

## Solution

Our solution is a parallel implementation using Go. An alternative distributed version can be found in my GoLServer and GoLClient repositories.

A skeleton project was provided including SDL. We developed the simulation logic in the `gol` directory.

For a description of how our solution works, see `report.pdf`.

## How to run

- `go test -v -run=TestGol/-n$` (where 1 ≤ n ≤ 16) tests the code with n workers.
- `go test -v -run=TestGol` runs all parallel tests.
- `go test -v -run=TestAlive` tests that the correct number of alive cells is reported every two seconds.
- `go test -v -run=TestPgm` tests that the result is output correctly.
- `go test -v` runs all above tests.

- `go run .` runs the simulation. With the SDL window open, press `s` to save, `q` to quit and `p` to pause/resume.

