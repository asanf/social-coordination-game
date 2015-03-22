# social-coordination-game
Code which computes approximated equilibrium for Social Coordination Games as shown by 
[E. Anshelevich and S. Sekar](http://arxiv.org/abs/1404.4718v1). 

## Usage

Given the number of players and strategies, the code generates a random instance. To create a game with ten players
and four strategies, simply type

```python
game = Game(10, 4)
```

Then you can normalize the weights and find an alpha approximated Nash equilibria with

```python
game.normalize()
result = game.findEquilibria(alpha)
```

result is a dictionary containing several info.
There are utility functions to save the results of a test as a CSV file. Furthermore, a function to make batch test in
parallel is available. The function ```run``` calls a given function for a given number of test cases.
The default test function tries several heuristic developed during my master thesis work. For example, to test
2500 instances of the game, with random number of players and strategies, type

```python
res = saveCSVResults( run(2500) )
```
this saves the results in a CSV file in the running directory and puts the same results in the variable res.
