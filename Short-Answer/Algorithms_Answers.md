#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
The runtime complexity of this algorithm is O(n). a gets incremented at every turn by the sum of itself an n^2, so at a certain point it will get to n^3 (i.e (a=n) * n * n )which matches the polynomial order of n in the loop.

b)
The runtime complexity of this block of code is O(n log n). The outer loop runs in linear time (i.e n times) while the inner loop runs in logarithmic time O(log n) given that it is getting doubly incremented at each turn. If you multiply the runtime complexities of the loops, you get a runtime complexity of O(n log n) (linearithmic). 

c)
The runtime complexity of this block of code is O(n) (where n is bunnies). The code runs recursively for n number of times and is decremented by 1 on each call to bring it closer to the base case. 


## Exercise II
My proposed algorithm implements a binary search approach where the egg is dropped from the middle floor (n / 2). If the egg breaks, you get rid of all the floors above it since surely any floor higher than the anchor cannot minimize instances of breakage. If the egg doesn't break, however, you get rid of the floors below it. This process continues until there's just two floor lefts and the higher of the two could considered to be f. 

The proposed algorith has a logarithmic runtime complexity of O(log n)

```
def minimize_broken_eggs_on_dropping(floors_list):
    # find middle floor
    mid_floor = len(floors_list) // 2

    # run code while there are at least 3 floors left
    while len(floors) > 2:

        # if the egg breaks, eliminate higher floors
        if egg_breaks(mid_floor):
            return minimize_broken_eggs_on_dropping(floors[:middle_floor])

        # if the egg doesn't break eliminate lower floors.
        elif not egg_breaks(mid_floor):
            return minimize_broken_eggs_on_dropping(floors[mid_floor + 1:])

    # return the higher floor in the two floors left
```