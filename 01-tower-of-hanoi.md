# Tower of hanoi

The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules: 
1. Only one disk can be moved at a time.
2. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack or on an empty rod.
3. No larger disk may be placed on top of a smaller disk.

Note: With 3 disks, the puzzle can be solved in 7 moves. The minimal number of moves required to solve a Tower of Hanoi puzzle is 2n − 1, where n is the number of disks. 

1. Move N-1 disks from left to middle.
2. Move largest disk from left to right.
3. Move N-1 disks from middle to right.


```python
def tower_of_hanoi(n, left='left', right='right', middle='middle', count=0):
    if n >= 1:
        count += 1
        count = tower_of_hanoi(n - 1, left, middle, right, count)
        print(left, '-->', right)
        count = tower_of_hanoi(n - 1, middle, right, left, count)
        return count
    else :
        return count
```


```python
import unittest
```


```python
class TestExample(unittest.TestCase):
    """Use unittest in Jupyter."""
    
    def test(self):
        print('--------------Case (3) can be solved in 7 moves----------------')
        self.assertEqual(tower_of_hanoi(3), 7)
        print('--------------Case (4) can be solved in 15 moves----------------')
        self.assertEqual(tower_of_hanoi(4), 15)
```


```python
if __name__ == '__main__':
    unittest.main(argv=['first-arg-is-ignored'], exit=False)
```

    .

    --------------Case (3) can be solved in 7 moves----------------
    left --> right
    left --> middle
    right --> middle
    left --> right
    middle --> left
    middle --> right
    left --> right
    --------------Case (4) can be solved in 15 moves----------------
    left --> middle
    left --> right
    middle --> right
    left --> middle
    right --> left
    right --> middle
    left --> middle
    left --> right
    middle --> right
    middle --> left
    right --> left
    middle --> right
    left --> middle
    left --> right
    middle --> right
    

    
    ----------------------------------------------------------------------
    Ran 1 test in 0.009s
    
    OK
    

Resources
- https://www.mathsisfun.com/games/towerofhanoi.html
- https://en.wikipedia.org/wiki/Tower_of_Hanoi
- https://medium.com/100-days-of-algorithms/day-1-hanoi-tower-94871efb7df3


```python

```
