# CMPS 2200 Assignment 5
## Answers

**Name:**___Noelle Fox___



- **1a.**
  - The maximum depth of a _d_-ary heap is Θ(logd n)
    - n = number of elements in the heap

- **1b.**
  - delete-min: W(n) = O(d(logd n))
  - insert: W(n) = O(logd n)
    - n = number of elements in the heap

- **1c.**
  - O((d|V| + |E|)logd |V|)

- **1d.**
  - d = Θ(log |V|)
 
- **2a.**
APSP(0,0,-1) = 0
APSP(0,1,-1) = -2
APSP(0,2,-1) = 2
APSP(1,0,-1) = ∞
APSP(1,1,-1) = 0
APSP(1,2,-1) = 1
APSP(2,0,-1) = ∞
APSP(2,1,-1) = ∞
APSP(2,2,-1) = 0

APSP(0,0,0) = 0
APSP(0,1,0) = -2
APSP(0,2,0) = 2
APSP(1,0,0) = ∞
APSP(1,1,0) = 0
APSP(1,2,0) = 1
APSP(2,0,0) = ∞
APSP(2,1,0) = ∞
APSP(2,2,0) = 0

APSP(0,0,1) = 0
APSP(0,1,1) = -2
APSP(0,2,1) = -1
APSP(1,0,1) = ∞
APSP(1,1,1) = 0
APSP(1,2,1) = 1
APSP(2,0,1) = ∞
APSP(2,1,1) = ∞
APSP(2,2,1) = 0


APSP(0,0,2) = 0
APSP(0,1,2) = -2
APSP(0,2,2) = -1
APSP(1,0,2) = ∞
APSP(1,1,2) = 0
APSP(1,2,2) = 1
APSP(2,0,2) = ∞
APSP(2,1,2) = ∞
APSP(2,2,2) = 0

- **2b.**
  - I noticed that APS(i,j,1) and APS(i,j,2) are exactly the same and that APS(i,j,0) is almost completely the same with one value differing
  - APSP(i,j,2) = min(APSP(i,j,1), APSP(i,2,1) + APSP(2,j,1))
  - and APSP(i,j,1) = min(APSP(i,j,0), APSP(i,1,0) + APSP(1,j,0))


- **2c.**
  - APSP(i,j,k) = min(APSP(i,j,k-1), APSP(i,k,k-1), APSP(k,j,k-1))

- **2d.**
  - there are n^3 subproblems
  - each subproblem does O(1) work, so the total work for the problem is W(n) = O(n^3)

- **2e.**
  - our W(n) = O(n^3), Johnson's W(n) = O(|V||E| + |V|^2 log|V|)
  - Our dunamic programming algorithm is generally preferable if we are working with a graph that has negative edge weights but no negative cycles. This is because it can handle the negative edges directly whereas the Johnson's algorithms needs to rewrite the edges and do extra work before it can begin to deal with negative values. 



- **3a.**
  - No, a solution to the MST is not GUARANTEED to be a solution to the MMET. Upon first glance it appears that it is because the total edge weight in an MST is already miniized; however, the MMET variation is focused on minimizing the maximum weight edge of any edge in the spanning tree. THerefore, an MST could contain a relatively heavy edge and a different tree could sacrifice some of the total weight to attain a smaller maximum edge weight.


- **3b.**
  - The easiest way I can think of to return the tree with the next lowest weight is to slightly modify the MST to check alternate trees by removing or swapping edges. This would entail computing the MST normally first. After this for each edge 'e' in the MST you would remove edge e, try to add another edge that connects the two components you just split, and compute the total weight of the new tree. You would then want your code to return the tree with the lowest total weight among all these options, also known as the "next-best tree".


- **3c.**
  - The total work = O(|E|log|V| + |V||E|)
