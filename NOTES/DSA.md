- [Algorithm Analysis](#algorithm-analysis)
  - [Complexity and Big O Notation](#complexity-and-big-o-notation)
- [Linear Search Algorithm](#linear-search-algorithm)
- [Binary Search Algorithm](#binary-search-algorithm)


# Algorithm Analysis

## Complexity and Big O Notation
- **Complexity** of an algorithm is simply the time and space required by the algorithm to process an input of given size
- Unless otherwise stated, complexity always refers to the worst case complexity
- In case of linear search:
    - **Time complexity** (aka running time) will be `cN` assuming `N` is the size of list and `c` depends on no. of operations we are perform in each iteration. Time complexity is proportional to the size of the input
    - **Space complexity** is some constant `c'` (independednt of N) since we need only a constant amount of space in computers memory (RAM) coz we will keep on updating the same variable
- To represent the worst case complexity we use the **Big O notation**.
- In Big O notation we drop any fixed constants and lower powers of variables to capture the relationship between size of input and complexity of algorithm
- Example, if complexity of algorithm is `cN^3 + dN^2 + eN + f`, then in Big O notaton it is represented as `O(n^3)`
- Thus **time complexity of linear search is O(N) and space complexity is O(1)**

# Linear Search Algorithm
- Time complexity : `O(N)`
- Space Complexity : `O(1)`
```python
def locate_card_linear(cards, query):
    position = 0
    while position < len(cards):
        if cards[position] == query:
            return position
        position += 1
    return -1
```

# Binary Search Algorithm
- Time complexity : `O(log N)`
    - explaination -> N, N/2, N/4, N/8 => N/2^k => k=log N
- Space Complexity : `O(1)`

```python
# EXAMPLE - 1 (input list in desc order without duplicates)
def locate_card(cards, query):
    lo = 0
    hi = len(cards)-1
    
    while lo <= hi:
        mid = (lo+hi)//2
        
        print(f'lo -> {lo}, hi -> {hi}, mid -> {mid}')
        
        if cards[mid] == query:
            return mid
        elif cards[mid] < query:
            hi = mid-1
        elif cards[mid] > query:
            lo = mid+1
    return -1

c = [89,67,56,45,9,8,7,2,1]
q = 2
print(locate_card(c,q))

####### OUTPUT
lo -> 0, hi -> 8, mid -> 4
lo -> 5, hi -> 8, mid -> 6
lo -> 7, hi -> 8, mid -> 7
7
```

```python
# EXAMPLE - 2 (input list in desc order with duplicates)
def test_location(cards, query, mid):
    mid_number = cards[mid]
    
    if mid_number == query:
        if mid-1 >= 0 and cards[mid-1] == query:
            return 'left'
        else:
            return 'found'
    elif mid_number > query:
        return 'right'
    elif mid_number < query:
        return 'left'
        

def locate_card(cards, query):
    lo = 0
    hi = len(cards)-1
    
    while lo <= hi:
        mid = (lo+hi)//2
        check = test_location(cards, query, mid)
        
        print(f'lo -> {lo}, hi -> {hi}, mid -> {mid}')
        
        if check == 'found':
            return mid
        elif check == 'left':
            hi = mid-1
        elif check == 'right':
            lo = mid+1
    return -1

c = [89,67,56,45,9,8,7,2,2,2,2,1]
q = 2
print(locate_card(c,q))

######## OUTPUT
lo -> 0, hi -> 11, mid -> 5
lo -> 6, hi -> 11, mid -> 8
lo -> 6, hi -> 7, mid -> 6
lo -> 7, hi -> 7, mid -> 7
7
```

```python
# GENERIC BINARY SEARCH ALGORITHM EXAMPLE
def binary_search(lo, hi, condition):
    while lo <= hi:
        mid = (lo+hi)//2
        result = condition(mid)
        if result == 'found':
            return mid
        elif result == 'left':
            hi = mid-1
        else:
            lo = mid+1
    return -1

def locate_cards(cards, query):
    lo, hi = 0, len(cards)-1
    
    def condition(mid):
        if cards[mid] == query:
            if mid-1 >= 0 and cards[mid-1] == query:
                return 'left'
            else:
                return 'found'
        elif cards[mid] > query:
            return 'right'
        else:
            return 'left'
    
    return binary_search(lo, hi, condition)

c = [89,67,56,45,9,8,7,2,1]
q = 2
print(locate_card(c,q))
print('\n')
c = [89,67,56,45,9,8,7,2,2,2,2,1]
q = 2
print(locate_card(c,q))

####### OUTPUT
lo -> 0, hi -> 8, mid -> 4
lo -> 5, hi -> 8, mid -> 6
lo -> 7, hi -> 8, mid -> 7
7

lo -> 0, hi -> 11, mid -> 5
lo -> 6, hi -> 11, mid -> 8
lo -> 6, hi -> 7, mid -> 6
lo -> 7, hi -> 7, mid -> 7
7
```