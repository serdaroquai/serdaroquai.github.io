---
layout: post
title:  "Shortest Subarray with sum at least K"
date:   2019-01-02 21:54:01 +0300
categories: algorithms
---
## Shortest subarray with sum at least K
https://leetcode.com/problems/shortest-subarray-with-sum-at-least-k/

* What makes this problem hard (and not solved by two pointers is negative numbers)
* Make a sum array such that `sum[i] = A[0] + A[1] + .. + A[i-1]`
* At this point if we pick every pair of elements and check if their sum difference is >= K we find our answer in `O(n^2)`
* Create a Deque `d` to store **indices** (we need the posiiton) of increasing sums. Two intuitions:
    - if `sums[i] - sums[d.peekFirst()]` is a solution it is always going to be a shorter solution than `sums[i+1] - sums[d.peekFirst()]`, so we can safely remove head of deque.
    - if `sums[d.peekLast()] >= sums[i]` in that case `sums[d.getLast()]` can never be a minimum solution since the solution before it is a higher sum with a lower index so remove tail of deque.    
* Every element gets in the queue once and gets out once. Therefore time complexity is `O(n)`
```java
...
for (int i=0; i<l+1; i++) {
    while (!d.isEmpty() && sums[i] - sums[d.peekFirst()] >= K) min = Math.min(min, i - d.pollFirst());
    while (!d.isEmpty() && sums[d.getLast()] >= sums[i]) d.pollLast();
    d.addLast(i);
}
```
