# dining-philosphers
c++ dining philosophers school assignment, multi threaded

This was a programming assignment for my Operating Systems and Architecture class
For this assignment, I needed to implement a simulation of Dijkstra's solution to the Dining Philosphers problem using threads, locks, and condition variables.

An explanation of the Dining Philosphers problem: You are observing a table with five philosphers, five bowls of food, and five forks.
Philoshpers must alternately think and eat, but can only eat if they are holding the fork to the left and right of them.
This problem is used to show a problem with multiple threads called deadlock, and this solution is one way to avoid deadlocks.

Dijkstra's Solution
Edsgar Dijkstra's	original solution to the Dining Philosophers problem used	semaphores,	but	it can
be adapted to use monitors as well.

Each philospher is in one of three state: THINKING, HUNGY, or EATING.

Every	philosopher starts out in	the	THINKING state.	
  
When a philosopher is	ready	to eat,	her	state	is changed to	HUNGRY.	
  
Before she can eat,she must test to see if it is safe to do	so. If either of her neighbors
is in the EATING state, it is not safe for her to eat and she must wait until the
situation chages, at which point her state is changed to EATING.

When a philospher is done eating, her state is changed to THINKING and she must
test to see if either of her neighbors is in the HUNGRY state and it is now safe for
them to eat. If it is, she must notify that philospher that it is now safe to start
eating.

Note that the same test is used to assure two different requirements of the problem:

  1. Safety: a philosopher only eats if it is safe to do so.
  2. Liveness: no philosopher should go hungry if it is safe to eat.
