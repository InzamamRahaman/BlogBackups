
 


## **Motivation**

Imagine that you are an adventurer archaeologist, that watched Indiana Jones many times in your impressionable youth and was affected incorrigibly by it, and that you have stumbled upon the treasure trove of some ancient king. Being an adventurer archaeologist is wrought with hefty expenses – airfare,  vaccinations for exotic diseases, dusters, ect.. Naturally you want to maximize the profit you would gain from selling the treasures you have just found. However, you came somewhat unprepared for such a bountiful find, and you brought with you a single satchel to carry artifacts back with you. You, being an experienced adventurer, have a good estimate of the potential profit of each artifact, the maximum weight your satchel can hold, and the weight of each artifact. Which artifacts do you take to maximize your profit ?

Now imagine that you are a sales representative for a pharmaceutical start-up (do those exist ?). Your company has derived a new antibiotic that is going to change the world. To spread the word about this new wonder drug, your company wants to send you on a journey around the country promoting said drug; however, they give you some authority over your trip – they have a set of cities that they want you to visit, but they are allowing you to select the ordering in which you visit the cities. Each of the cities have direct flights to every other city in the list (if we were to represent the cities as vertices and flights as edges in a graph, our graph would be isomorphic to Kn, where n is the number of cities). Given the flight times, how can you derive the path of cities you can take to minimize the length of your trip ?

Both of these problems are combinatorical optimization problems. In both of them there is some selection or arrangement that is optimal with respect to some criteria, which we call the objective function, and we endeavor to find such optimal arrangement or selection. The first problem is an instance of the 0/1-knapsack problem, and the second is an instance of the infamous traveling salesman problem. The hope of finding the solutions to such optimization problems as been an impetus for much of Computer Science and Mathematics. Unfortunately, solving some of these optimization problems is much easier said than done.

The naive way to approach a combinatorical optimization problem would be to process every possible combination and apply the objective function to each – a very inefficient approach. To illustrate why this is a bad idea, let us look at the 0/1 knapsack problem. In the 0/1 knapsack problem, we have two possible “moves” for each item – to take it or leave it. Consequently, for a 0/1 knapsack problem where we have n items, we have 2^n possible combinations! For the traveling salesman problem, enumerating and testing all solutions becomes even more infeasible – there are n! possibilities.

Since, we brute force algorithms are infeasible, we can use other techniques to try to yield a solution in a reasonable time frame depending on the structure of the solutions. For example, since the 0/1 knapsack problem possess an optimal substructure, we can leverage dynamic programming to solve an instance of it in pseudo-polynomial time. We can use a technique called Branch and Bound to navigate the search space in a more efficient manner, omitting branches that we can predict would lead to non-optimal possibilities. While we want our programme’s output to be the optimal solution, sometimes we can settle for approximations to the solution, and one approach we may use to accomplish this is by using the genetic algorithm.

 


## **Core Ideas of the Genetic Algorithm**

When one hears the term genetic algorithm it can conjure up pictures of things like DNA strands, with their constituent nucleotides colour coded, mutated fruit flies, and possibly a Marvel comic character or two. If this is true for you, then you already have quite a bit of the intuition you need to leverage the genetic algorithm to solve basic combinatorical optimization problems. The genetic algorithm and its oft confused cousin, genetic programming, are attempts to replicate the process of natural selection.


