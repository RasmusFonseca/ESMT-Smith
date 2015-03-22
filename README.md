
# Finding Steiner minimal trees in euclidean d-space

The Euclidean Steiner Minimal Tree (ESTP) problem seeks a network of minimal total edge length spanning a set of n terminal points while allowing for the insertion of additional points (Steiner points) to decrease the overall length of the network.

Smith [1] designed an iterative method for optimizing the positions of Steiner points in the network, given a topology and terminal positions. By inserting terminals into existing edges, topologies can be expanded and a backtracking method (branch-and-bound) can exactly identify topologies with minimal corresponding network. 

This repository contains Smith's original C-code verbatim from the pdf version of the paper as well as an updated version that has been updated to compile on GCC 4.2 (but with no changes to the logic of the program).

* [1] Warren D. Smith. How to find Steiner minimal trees in euclidean d-space. Algorithmica (1992) Volume 7, Issue 1-6, pp 137-177

# Compiling

```
$ cd src
$ make
```

# Usage

The executable `src/smith_original` takes no arguments, but reads from standard in. The expected format is
* Line 1: Integer number of terminals (n)
* Line 2: Integer number of dimensions (d)
* Line 3 to n+2: Double precision coordinates separated by spaces

# Example usage

```
$ src/smith_original < paper_instances/icosahedron.txt
NUMSITES = 12
DIMENSION = 3
 1 0 1.61803
 0 1.61803 1
 1.61803 1 0
 -1 0 1.61803
 0 1.61803 -1
 1.61803 -1 0
 1 0 -1.61803
 0 -1.61803 1
 -1.61803 1 0
 -1 0 -1.61803
 0 -1.61803 -1
 -1.61803 -1 0
SCALE = 3.23607
...
new record length 18.55289840234281229
topology-describing vector: 1 3 3 8 4 6 14 12 18
steiner point coords
 0.24215879379976976149 0.93215507190477320254 0.67804170788173667717
 0.26588748637834835886 0.20619172339298974528 1.1633247674682358763
 0.43231772672551771475 0.9107507253045512563 0.019451825976701198062
 1.1292168896194123562 0.67350148197410231177 -0.16703650265950753528
 1.2200135837716867826 0.020713963783942968 -0.56710550298612527609
 -0.32640608115631269959 -0.23729614918451341632 1.1954370958132951586
 -0.14472572625909763122 1.1641295080729872069 -0.62456829729923024619
 -0.82541110453009869374 0.80239262073650374774 -0.69873703697421640779
 -0.3145143929280325712 -1.1142080503655515944 0.7336734124780507349
 -0.67220808263149389727 -1.198266626201165419 0.069396426690139331739
edges
1-14;2-13;3-16;4-18;13-14;5-19;13-15;6-17;15-16;7-17;16-17;8-21;14-18;9-20;15-19;10-20;19-20;11-22;18-21;12-22;21-22;
...
done
```
