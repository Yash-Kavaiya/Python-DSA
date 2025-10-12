## Two Sum Problem - Optimized Solution

The brute force approach with nested loops has **O(n²) time complexity**, which causes Time Limit Exceeded (TLE) for large inputs (10⁵ elements). The optimized solution uses a **hashmap** to achieve **O(n) time complexity**.[1][2][3][4]

### How the HashMap Approach Works

Instead of checking every pair, store each number and its index in a hashmap while iterating once. For each element, calculate the complement (`target - current_number`) and check if it already exists in the hashmap.[5][6][1]

```python
def two_sum(nums, target):
    hashmap = {}
    
    for i, num in enumerate(nums):
        complement = target - num
        if complement in hashmap:
            return [hashmap[complement], i]
        hashmap[num] = i
    
    return [-1, -1]
```

**Complexity Analysis:**
- **Time:** O(n) - single pass through the array[4]
- **Space:** O(n) - hashmap stores up to n elements[3]

## Contains Duplicate - Optimized Solution

The nested loop approach also has **O(n²) complexity**. The optimal solution uses a **HashSet** to track seen elements in a single pass.[7][2][8]

### HashSet Approach

Add each element to a set while checking if it already exists. If found, immediately return `True`; otherwise, continue until the array ends.[9][7]

```python
def contains_duplicate(nums):
    seen = set()
    
    for num in nums:
        if num in seen:
            return True
        seen.add(num)
    
    return False
```

**Complexity Analysis:**
- **Time:** O(n) - single iteration[8]
- **Space:** O(n) - set stores unique elements[9]

### Why O(n²) Fails

With array lengths up to 10⁵, nested loops perform 10¹⁰ operations, exceeding the typical 10⁸-10⁹ operation limit for online judges. Hash-based solutions reduce this to 10⁵ operations, easily passing all test cases.[2][10][8][4]

