# moopt-hackathon-1 Marshalling Challenge
Repository containing the files necessary for the first Moopt hackathon challenge

## About the project
This repository contains all the relevant information about the first Moopt hackathon challenge to be held in September 2021. 

The challenge is divided into two parts. The first is an exercise with a small scale toy instance that can be solved by hand. The purpose of this is so that the contestants can easily check if their models are correct by verifying that their proposed 
solution is feasible and optimal. The second part consists of the releasing of large scale instances that cannot be solved by hand but whose feasibility and quality will be evaluated by an automated script. Contestants will be ranked based on the feasible 
solutions with the least number of moves (below details will clarify the use of this metric)

## Problem Statement and Context
The following problem was encountered as a component of an industrial project deployed at a logistics company. With the arrival of IoT, this company is preparing its decision support tools to automate logistic operations to optimize the 
number of "transactions" required to achieve its tasks.

The context from which this particular challenge arrives is the marshalling of railcars arriving at a port into trains bound for the same direction (North, South, East, West). Unlike the classical train marshalling problem which seeks to determine
the number of tracks needed to create this split, in this problem context, the marshalling tracks and their format (location of bridge tracks as well as length before and after bridge tracks) are fixed. 

Railcars arrive based on the order in which their contents were disembarked and assembled at the port and thus their sequence contains no obvious sequence based on their destination's direction (initial state). The client's task is to reaccommodate this sequence of 
railcars into the respective tracks designated for each direction. 


## Goal
Given an initial state, find the smallest sequence of legal moves to reach a target final state.

## Rules:
* A move is the displacement of a group of adjacent railcars from one track to another. 
	(e.g. [R7, R8]: PG9E → PG9W is one move)
* Railcars can move from a track to another only if there is an arrow between them. 
	(e.g., No railcars can move from PG9E to PG10W)
* The stacking rule followed by the railcars on the tracks is LIFO (last in first out). 
	(e.g.: [R7]: PG9E → PG9W is not a legal move)
	
	
## Final state:
•	All the orange railcars (R2, R3) must be anywhere on the PG9E track.
•	All the yellow railcars (R1, R4, R5, R6, R8) must be anywhere on the PG10E track.
•	All the red railcars (R7) must be anywhere on the PG9W track.
