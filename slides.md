---
theme: seriph
title: "MTH252"
background: https://mth252.fastzhong.com/images/cover.webp
highlighter: shiki
lineNumbers: false
colorSchema: "light"
---

# MTH252

Data Structures and Algorithms II

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Zhong Lun
  </span>
</div>

---

# About Me

<br/>

<i class="fab fa-linkedin"></i> [https://www.linkedin.com/in/zhonglun/](https://www.linkedin.com/in/zhonglun/)  
<i class="far fa-envelope"></i> [zhonglun@gmail.com](zhonglun@gmail.com)  
<i class="fas fa-mobile-alt"></i> 9647 7009

<br/>

<img src="/images/linkedin.png" style="border-radius: 8px; width:50%"/>

---

# Course Structure

<br/>

<div grid="~ cols-2 gap-4">
  <div>
    6 weeks (Jan ~ Mar), 6 seminars & 6 labs:
    <p class="norm">
      <ol>
        <li><span class="hl-bg">Priority Queue</span>, <span class="hl-bg">Binary Heap</span>, <span class="hl-bg">Hash Table</span> & <span class="hl-bg">Skip List</span></li>
        <li>Search Trees: <span class="hl-bg">Binary Search Tree</span>, <span class="hl-bg">AVL</span></li>
        <li>Sorting: <span class="hl-bg">Merge-Sort</span>, <span class="hl-bg">Quick Sort</span> <br/> Selection: <span class="hl-bg">Prune-and-Search</span>, <span class="hl-bg">Randomized-Quicksort</span></li> 
        <li>Text Processing: <span class="hl-bg">Brute-Force</span>, <span class="hl-bg">Boyer-Moore</span>, <span class="hl-bg">Knuth-Morris-Pratt</span>(KMP) and <span class="hl-bg">Dynamic Programming</span>(DP)</li> 
        <li>Graph: <span class="hl-bg">Depth-First Search</span>, <span class="hl-bg">Breadth-First Search</span>, <span class="hl-bg">Dijkstra's Shortest Path</span>, <span class="hl-bg">Min-Spanning Tree</span>, and <span class="hl-bg">Directed Acyclic Grap</span>(DAG) </li>
        <li>Review and more</li>
      </ol>
    </p>
  </div>
  <div>
    3 assignments & open book exam:
    <p class="norm">
      <img src="/images/assessment.png" style="width:80%"/>
    </p>
  </div>
</div>

---

# Slides & Notebooks

<br/>

slides online: [https://mth252.fastzhong.com/](https://mth252.fastzhong.com/)

<mdi-file-pdf /> [https://mth252.fastzhong.com/mth252.pdf](https://mth251.fastzhong.com/mth252.pdf)

<logos-github-octocat /> labs: [https://github.com/fastzhong/mth252/tree/main/public/notebooks](https://github.com/fastzhong/mth252/tree/main/public/notebooks)

<br/>

<br/>

👉 Python & Big O review: [MTH251 lab1](https://mth252.fastzhong.com/)

<br/>

<p class="norm">
🏃‍♂️ learning by doing, implementing the algo from scratch  <br/>
🙇🏻‍♂️ problem solving 
</p>

---

# Learning Resource

[📚 books](https://github.com/fastzhong/mth251/tree/main/public/resources)

<div grid="~ cols-4 gap-4">
  <div><img src="/images/study_guide.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/study_book.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/common-sense.jpg" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/grokking.jpg" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/algorithms.png" style="width: 140px; height: 180px"/></div>
  <div><img src="/images/intro_algorithms.png" style="width: 140px; height: 180px"/></div>
</div>

---

# Learning Resource

📚 books

if you want to dive deeper into proofs and the mathematics of computer science:

[Building Blocks for Theoretical Computer Science](https://mfleck.cs.illinois.edu/building-blocks/index-sp2020.html) by Margaret M. Fleck


---

# Clarification on DSA questions

<br/>

Algo implementation in related DSA questions:

-   always seek the best time and space complexity by appling DSA taught in MTH251 & MTH252  
-   in principle, only the standard ADT operations allowed to use by default as the solution has to be language indenpendent    
-   advanced features and built-in functions from Python not allowed if not clearly asked by the question, e.g. sort/search/find (in)/min/max/set/match ... , as the algo implementation becomes unknown and Python dependent 
 

---
layout: center
---

# Priority Queue


---

# Priority Queue

<br/>

-   FIFO/LILO
-   <span class="hl">each element (k, v) has a certain priority k and k must be compariable</span>
-   min priority queue (smaller k, higher priority)
-   max priority queue (bigger k, higher priority)

<br/>

<span class="norm">e.g. printer queue, cpu task scheduler, etc.</span>

<!--
You cannot sort the elements/tasks first, and pick up the highest task, as the first task is finished, there could be some new coming tasks. in another word we need a data structure to DYNAMICALLY maintain the ordering.
-->

---

# Priority Queue: Operations (Min PQ)

<br/>

-   <span class="hl-strong">add(k, v)</span> (enqueue) − adding an element to the queue
-   <span class="hl-strong">remove_min()</span> (dequeue) − obtain the first element with a pair of (k,v), where k is the mininum value of keys in Min PQ, and remove it from the queue
-   <span class="hl-strong">min()</span> (first/peek) − obtain the first element with a pair of (k,v) where k is the mininum value of keys in Min PQ
-   size(), is_empty()

---

# Priority Queue Complexity

<logos-jupyter />

<br/>

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="30%">unsorted list</th>
        <th id="" width="30%">sorted list</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>is_empty</th>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="even">
        <th>size</th>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>add</th>
        <td>O(1)</td>
        <td>O(n) 👈 </td>
      </tr>
      <tr class="even">
        <th>remove_min</th>
        <td>O(n) 👈 </td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>min</th>
        <td>O(n) 👈 </td>
        <td>O(1)</td>
      </tr>
    </tbody>
  </table>
</div>

--- 
layout: center
---

# Binary Heap

---

# Binary Heap

<br/>

-   <span class="hl">Complete Binary Tree</span>

-   k value for any node in the tree <span class="hl">smaller than any child node</span>

<br/>

<img src="/images/binary_heap.png" style="width: 80%"/>

<br/>

<span class="norm">👉 A <strong>complete binary tree</strong> is a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible.
</span>

---

# Binary Heap

<br/>

-   from root to any leaf, the key values are in non-decreasing order

-   key of root is always the smallest

-   given height $h$, total nodes of binary heap: $2^h \leq n \leq 2^{h+1} - 1$

-   given total nodes $n$, binary heap height: $\log_2(n+1) - 1 \leq h \leq \log_2n$

<!--
if exclude the bottom level, binary heap is a perfect binary tree and nodes is 2^h - 1

low level node is always smaller than the high level node? NO.
-->

---

# Binary Heap

<br/>

<div grid="~ cols-2 gap-12">
  <div>
    <img src="/images/binary_heap_index.png"/>
  </div>
  <div>
    <br/>
    <table class="grid">
      <tbody>
        <tr class="odd">
          <td>2</td>
          <td>4</td>
          <td>3</td>
          <td>5</td>
          <td>6</td>
          <td>6</td>
          <td>9</td>
          <td>6</td>
          <td>7</td>
          <td>8</td>
        </tr>
        <tr class="even">
          <td>0</td>
          <td>1</td>
          <td>2</td>
          <td>3</td>
          <td>4</td>
          <td>5</td>
          <td>6</td>
          <td>7</td>
          <td>8</td>
          <td>9</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div></div>
  <div>
    <table style="width:60%; font-family: 'Open Sans'; font-size: 0.8rem;">
      <tbody>
      <tr>
        <td align="right">parent(i)</td>
        <td align="center">=</td>
        <td align="left">(i - 1) / 2</td>
      </tr>
      <tr>
        <td align="right">left_child(i)</td>
        <td align="center">=</td>
        <td align="left">2 * i + 1</td>
      </tr>
      <tr align="left">
        <td align="right">right_child(i)</td>
        <td align="center">=</td>
        <td align="left">2 * i + 2</td>
      </tr>    
      </tbody>
    </table>  
  </div>
</div>
---

# Binary Heap

<logos-jupyter />

<br/>

-   add new element:

    1. append to the last (so its still complete binary tree)
    2. "sift up" if new element is smaller

-   remove the min:
    1. replace the first element with the last (so its still complete binary tree)
    2. "sift down" if the last element is bigger

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/Heap.html](https://www.cs.usfca.edu/~galles/visualization/Heap.html)</span>

---

# Priority Queue Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="25%">Operation</th>
        <th id="" width="25%">unsorted list</th>
        <th id="" width="25%">sorted list</th>
        <th id="" width="25%">binary heap</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>is_empty</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="even">
        <th>size</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
      <tr class="odd">
        <th>add</th>
        <td>O(1)</td>
        <td>O(n)</td>
        <td>O(logN) 👈 </td>
      </tr>
      <tr class="even">
        <th>remove_min</th>
        <td>O(n)</td>
        <td>O(1)</td>
        <td>O(logN) 👈 </td>
      </tr>
      <tr class="odd">
        <th>min</th>
        <td>O(n)</td>
        <td>O(1)</td>
        <td>O(1)</td>
      </tr>
    </tbody>
  </table>
</div>

<!--
Binary Heap is always a complete binary tree, so the height is always O(logN), note that the worst case of binary tree is O(N) == linked list.
-->

---

# When & Where 

<br/>

Priority Queue (PQ) is used: 

-   used in certain implementations of <span class="hl-bg">Dijkstra's Shortest Path</span> algorithm

-   <span class="hl-bg">Best First Search</span> (BFS) algorithms such as A\* uses PQ to continuously grab the next most promising node

-   used in <span class="hl-bg">Huffman coding</span> (which is often used for lossless data compression)

-   used by <span class="hl-bg">Minimum Spanning Tree</span> (MST) algorithms

-   anytime you need to dynamically fetch the "next best" or "next worst" element

-   ...

<!--
Technically Priority Queue can be considered same as binary heap, but Priority Queue is ADT as it can be implemented by other data structure.

There are trees other than binary tree, so there are heaps other than binary heap - D-ary Heap, Fibonacci Heap, Index heap, Binomial Heap, Pairing Heap, etc. But binary heap is very useful and important data structure.
-->

---

# Heap Sort

<logos-jupyter />

<br/>

1. create a binary heap

2. add all elements to the heap

3. recursively obtain the min/max element from the heap

---
layout: two-cols
---

# Heapify

<logos-jupyter />

<span class="hl">Heapify</span>: convert the array to be a binary heap

by "sift down" the non-leaf node one by one from bottom to top

Complete Binary Tree (Perfect Binary Tree)
|                       |                     |            |                             |
| --------------------: | :------------------ | ---------: | :-------------------------- |
|     last level nodes: | $\frac{n}{2}$       | sift_down: | $\frac{n}{2} * 0$           |
| 2nd last level nodes: | $\frac{n}{4}$       | sift_down: | $\frac{n}{4} * 1$           |
|                   ... |                     |        ... |                             |
| h+1 last level nodes: | $\frac{n}{2^{h+1}}$ | sift_down: | $\frac{n}{2^{h+1}} \cdot h$ |

::right::

<div align="center">

<br/>

<br/>

<br/>

Time Complexity: $O(n)$

<br/>

<img src="/images/heapify_complexity.png" style="width: 80%"/>

</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.6rem;
}
</style>


<!--
last non-leaf node: parent of last leaf node
-->

---
layout: two-cols
---

# Heap Sort

<logos-jupyter />

<br/>

```python
"""
heap_sort: sort nums in place

time complexity: O(N)
space complexity: O(1)
"""
def heap_sort2(nums: []) -> []:
    nums = heapify(nums)
    print("    heapify: ", nums)
    # swap from the last element
    for i in range(len(nums) - 1, 0, -1):
        # move the biggest to the end
        nums[0], nums[i] = nums[i], nums[0]
        # sift down the first element after swap
        # so nums[0, i) is still a max heap
        heapify_sift_down(nums, 0, i)
    return nums
```

::right::

<br/>

<br/>

<br/>

<img src="/images/heap_sort.png" style="height: 70%"/>

---
layout: center
---

# Map/Hash Table 

---

# Map

<br/>

A <span class="hl-bg">Map</span> is an abstract data structure (ADT):

-   a collection of key-value (k,v) paris
-   key can be viewed as a unique identifier for the object/value

k - unique  
v - can be repeated

<br/>

A <span class="hl-color">Sorted Map</span> is an extension of Map and keys are sorted in increasing order.

<br/>

<span class="norm">🤔 Can we use **none**/**null** for key?</span>

---

# Map

<br/>

class score:

| Student(key) | Score(value) |
| :----------- | :----------- |
| A:           | 80           |
| B:           | 70           |
| C:           | 60           |
| ...          | ...          |

---

# Map Operations

<br/>

for a map

<pre class="norm">
- map[k], map.get(k)
- map.pop(k)
- map[k] = v, map.set(k) = v, map.put(k,v), map.setdefault(k, default)
- map.keys()
- map.values()
- del map[k], map.clear()
- size(map)
- iter(map), map.items()
</pre>

---

# Map Operations

<br/>

for a sortedMap

<pre class="norm">
- sortedMap.find_min()
- sortedMap.find_max()
- sortedMap.find_lt(k)
- sortedMap.find_le(k)
- sortedMap.find_gt(k)
- sortedMap.find_ge(k)
- sortedMap.find_range(k1, k2)
- sortedMap.reversed()
</pre>

---

# Map Implementation

<br/>

-   Array/ArrayList
-   Linked List
-   Binary Search Tree
-   Hash Table

---

# Map Implementation: Linked List

<br/>

-   store (k,v) in a doubly linked list

-   get(k)

    -   <span class="norm">loop through the list until find the element with key k</span>

-   set(k,v)

    -   <span class="norm">create a new node (k,v) and add it at the front</span>

-   delete(k)
    -   <span class="norm">loop through the list until find the element with key k</span>
    -   <span class="norm">remove it by updating the pre and next elements</span>

<span class="norm">👉 Complexity: $O(n)$</span>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Table

<br/>

A <span class="hl-bg">Hash table</span> is a data structure that provides a mapping from keys to values using a technique called <span class="hl-color">hashing</span>.

A hash function <span class="hl-color">H(x)</span> is a function that maps a <span class="uline">general</span> key ‘x’ to a whole number in a fixed range [0, N-1].

💡 <span class="norm">locate the element without searching: </span>$O(n)$ → $O(1)$

<!--
large keys → small keys (indexable)
-->

---

# Hash Function

<br/>

step1. Hash Code: abitrary object → integer

<p class="norm">An element is converted into an integer by using a hash function. This element can be used as an index to store the original element, which falls into the hash table.
<br/>

```
hash = hashcode(key)
```

</p>

step2. Compression: $integer \in [0, N-1]$ (N is the size of hash table)

<p class="norm">
The element is stored in the hash table where it can be quickly retrieved using hashed key.
<br/>

```
index = hash % array_size
```

</p>

---

# Hash Code: Bit Representation

```python
# XOR byte by byte
def byte_xor(ba1, ba2):
    return bytes([_a ^ _b for _a, _b in zip(ba1, ba2)])

# produce 32-byte hash code
# chop the data into 32-byte long chunks (padding with zeros if required) then XOR on all chunks
def bitwise_xor(data):
    chunks = [data[i:i+32] for i in range(0, len(data), 32)]
    for i in range(len(chunks)):
        chunk = chunks[i]
        hexchunk = chunk.hex()
        len_diff = 32 - len(chunk)
        if len_diff:
            hexchunk += '00' * len_diff
            chunk = bytearray.fromhex(hexchunk)
            chunks[i] = chunk
    res = bytes.fromhex('00' * 32)
    for chunk in chunks:
        res = byte_xor(res, chunk)
    return res
```

👉 <span class="norm">[MD5](https://en.wikipedia.org/wiki/MD5)&nbsp;&nbsp;&nbsp; [SHA-256](https://en.wikipedia.org/wiki/SHA-2)</span>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Code: Polynomial & Cyclic-Shift

<br/>

### Polynomial

for n-tuple $(x_0, x_1, x_2, ..., x_{n-1})$, if position is important, we can multiply $a^{n-1}$ for position $n$, e.g.:

$x_0·a^0 + x_1·a^1  + x_2·a^2  + ...  + x_{n-1}·a^{n-1}$

### Cyclic-Shift

for bitwise, we can also apply cyclic-shift function instead of multiplication, e.g. shift(x, y) means cyclic-shift y bits:

$shift(x_0, 0\;mod\;32) \oplus shift(x_1, 1\;mod\;32)  \oplus shift(x_2, 2\;mod\;32)  \oplus ...  \oplus shift(x_{n-1}, (n-1)\;mod\;32)$

💬 5-bit cyclic shift operation can achieve the smallest total collisions when 230,000 English words

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Compression

<br/>

for hash code $x$:

-   Division Method: $x\;mod\;N$

-   MAD: $(a\;\cdot\;x + b)\;mod\;p$  
    where $p$ is a prime number, $p > N$, $a$ and $b$ are random number, $a\in[0, p-1]$, $b\in[0, p-1]$

<br/>

👉 <span class="norm">[good hash table primes](https://planetmath.org/goodhashtableprimes) </span>

---
layout: two-cols
---

# Hash Function

<br/>

a number of (k, v) pairs with key set {“abcdef”, “bcdefa”, “cdefab” , “defabc”}

The ASCII values of a, b, c, d, e, and f are 97, 98, 99, 100, 101, and 102 respectively.

| key    |             Hash Function              | Index |
| :----- | :------------------------------------: | :---- |
| abcdef | (97 + 98 + 99 + 100 + 101 + 102) % 599 | 2     |
| bcdefa | (98 + 99 + 100 + 101 + 102 + 97) % 599 | 2     |
| cdefab | (99 + 100 + 101 + 102 + 97 + 98) % 599 | 2     |
| defabc | (100 + 101 + 102 + 97 + 98 + 99) % 599 | 2     |

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hash_example1.jpeg" style="width:70%; height: 70%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---
layout: two-cols
---

# Hash Function

<br/>

a number of (k, v) with key set {“abcdef”, “bcdefa”, “cdefab” , “defabc”}

The ASCII values of a, b, c, d, e, and f are 97, 98, 99, 100, 101, and 102 respectively.

| key    |                 Hash Function                 | Index |
| :----- | :-------------------------------------------: | :---- |
| abcdef | (971 + 982 + 993 + 1004 + 1015 + 1026) % 2069 | 38    |
| bcdefa | (981 + 992 + 1003 + 1014 + 1025 + 976) % 2069 | 23    |
| cdefab | (991 + 1002 + 1013 + 1024 + 975 + 986) % 2069 | 14    |
| defabc | (1001 + 1012 + 1023 + 974 + 985 + 996) % 2069 | 11    |

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hash_example2.jpeg" style="width:70%; height: 70%"/>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}

table {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---
layout: two-cols
---

# Hash Function: Collision

<br/>

### chaining (open hashing)

-   one element: $O(1)$

-   more than one element: **linked list** $O(1) + O(n)$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/hash_chaining.png" style="width:60%"/>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Collision

### open address (closed hashing)

Finding an unused, or open, location in the hash table is called <span class="hl-strong">open addressing</span>.

The process of locating an open location in the hash table is called <span class="hl-strong">probing</span>.

Various probing techniques:

<br/>

<div grid="~ cols-3 gap-4">
  <div class="norm">
    <span class="hl">linear probing</span><br/><br/> 
    <img src="/images/probing_linear.svg"/><br/>    
    index = (index + 1) % hashTableSize<br/>  
    index = (index + 2) % hashTableSize<br/>  
    index = (index + 3) % hashTableSize<br/>  
    ...  
  </div>
  <div class="norm">
    <span class="hl">quadratic probing</span><br/><br/>  
    <img src="/images/probing_quadratic.svg"/><br/>   
    index = (index + 1^2) % hashTableSize<br/>  
    index = (index + 2^2) % hashTableSize<br/>  
    index = (index + 3^2) % hashTableSize<br/>  
    ... 
  </div>
  <div class="norm">
    <span class="hl">double probing</span><br/><br/> 
    <img src="/images/probing_double.svg"/><br/> 
    index = (index + 1 * H2) % hashTableSize<br/>  
    index = (index + 2 * H2) % hashTableSize<br/>  
    index = (index + 3 * H2) % hashTableSize<br/>  
    ... 
  </div>
</div>

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>

---

# Hash Function: Collision

<br/>

⚠️ probing may go into cycles (**an infinite loop**) (hashing attack)

⚠️ chaos when removing element from hash table

<br/>

<div grid="~ cols-2 gap-4" class="norm">
  <div>k % 10, linear probing, k1=11, k2=21, k3=31</div>
  <div>&nbsp;</div>
  <div>
    - put(k1,v1)&nbsp;&nbsp;&nbsp;(probing: 1)<br/>  
    - put(k2,v2)&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>
    - put(k3,v3)&nbsp;&nbsp;&nbsp;(probing: 1 → 2 → 3)<br/>
  </div>
  <div><img src="/images/hash_linear1.png"></div>
  <div>
    - del(k2)&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>  
    - <span style="color:red">get(k3)</span>&nbsp;&nbsp;&nbsp;(probing: 1 → 2)<br/>
  </div>
  <div><img src="/images/hash_linear2.png"></div> 
</div>

---
layout: two-cols
---

# Hash Table: resize

<br/>

$M$<span class="norm">: total num of map elements</span>  
$O$<span class="norm">: num of occupied buckets</span>  
$N$<span class="norm">: size of hash table</span>  
$P$<span class="norm">: new size of hash table (expand or shrink)</span>

when:

-   load factor (for open addressing): $\frac{O}{N}$
-   tolerance factor (for closed addressing): $\frac{M}{N}$

how:

-   size(<span class="norm">[good hash table primes](https://planetmath.org/goodhashtableprimes)</span>): $N$ → $P$
-   rehashing: $H(x)\;mod\;N$ → $H(x)\;mod\;P$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/hash_chaining.png" style="width:60%"/>

---
layout: two-cols
---

# Hash Function

-   $H(x)$ must be deterministic
-   $H(x)$ need to be fast $O(1)$
-   $H(x)\;mod\;N$ evenly distributed
-   if $x = y$, H(x) and H(y) <span class="uline">must be equal</span>
-   if $H(x) = H(y)$, x and y <span class="uline">might be equal</span>
-   if $H(x) \neq H(y)$, x and y <span class="uline">certainly not equal</span>

<br/>

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering

::right::

<br/>

<span class="norm">💡 coding tips:</span>

-   <span class="norm">avoid to use real or big number as key: $H(0.0) == H(-0.0)$ ⁇</span>
-   <span class="norm">compare hash code first, before compare x and y</span>
-   <span class="norm">overwrite either both of **eq** and **hash** or neither of them</span>

<br/>

```python
class UserGroup:

  def __init__(self, name, status):
    self.name = name
    self.status = status

  def __hash__(self):
    result = 17
    result = 31 * result + hash(name)
    if not status:
      result = 31 * result + hash(status)
    return result

  def __eq__(self, other):
    if isinstance(other, UserGroup):
      return self.__hash__() == other.__hash__()
    return False
```

---

# Map/Hash Table Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Operation</th>
        <th id="">avg case</th>
        <th id="">best case</th>
        <th id="">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---
layout: two-cols
---

# Industrial Implementation

 <logos-java/> HashMap

-   hash code

<table style="width:90%; font-family: 'Open Sans'; font-size: 0.8rem;">
  <tbody>
    <tr>
      <td align="right"><strong>Key Type</strong></td>
      <td align="left"><strong>hashCode(k)</strong></td>
    </tr>    
    <tr>
      <td align="right">boolean</td>
      <td align="left">k? 0 : 1</td>
    </tr>
    <tr>
      <td align="right">byte, char, short, int</td>
      <td align="left">k</td>
    </tr>
    <tr>
      <td align="right">long</td>
      <td align="left">(int)(k XOR (k >>> 32))</td>
    </tr>
    <tr>
      <td align="right">float</td>
      <td align="left">Float.floatToIntBits(k)</td>
    </tr>
    <tr>
      <td align="right">double</td>
      <td align="v">long l = Double.doubleToIntLongBits(k)<br/>(int)(l XOR (l >>> 32))</td>
    </tr>
    <tr>
      <td align="right">string/array</td>
      <td align="v">s[0]*31^(n-1) + s[1]*31^(n-2)+ ... + s[n-1]</td>
    </tr>
  </tbody>
</table>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">similarly for compound data type, like Object k with $n$ fields, a way to implement hashCode():</span>

$h = h(k_0)*31^{n-1} + h(k_1)*31^{n-2} + ... + h(k_{n-1})$

```java
String name;
int age;

@Override
public int hashCode() {
    int result = name != null ? name.hashCode() : 0;
    result = 31 * result + age;
    return result;
}
```

---
layout: two-cols
---

# Industrial Implementation

 <logos-java/> HashMap

-   compression/indexing: $h\;\&\;(n - 1)$

<span class="norm">when table size $n$ is $2^y$: </span> $x\;\%\;2^y = x\;\&\;(2^y - 1)$

<span class="norm">e.g.</span>

$6\;\%\;8 = 6$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$6\;\&\;7 = 6$  
$10\;\%\;8 = 2$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$10\;\&\;7 = 2$

<img src="/images/hashmap_index.webp" style="height:20%"/>

<br/>

<span class="norm">👉 binary bit operation <span class="hl">&</span> is much faster then decimal mod</span>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">then XOR between the first 16 bits and the last 16 bits:</span>

$H(k) =  (h\;XOR\;(h\;>>>\;16))\;\&\;(n - 1)$

<br/>

<div>
  <img src="/images/hashmap_hash.png" style="width:80%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

 <logos-java/> HashMap

-   Collision: chaining
    -   **linked list** $O(1) + O(n)$
    -   $< Java 8$, insert at the beginneing (⚠️ deadlock in concurrent insertion);  
        $> Java 8$, append to the tail
    -   **treemap/red black tree** (more than 8 elements and table size ≧ 64) $O(1) + O(logN)$

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/hashmap_collision1.jpeg" style="width:80%"/>
  <img src="/images/hashmap_collision2.png" style="width:80%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

 <logos-java/> HashMap

-   hash table size
    -   always $2^n$,&nbsp;&nbsp;&nbsp;default: $16$, &nbsp;&nbsp;&nbsp;max: $2^{30}$
    -   load factor: $0.75$
    -   optimize rehashing

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<span class="norm">size $16$ → $16 * 2$: </span>

<div>
  <img src="/images/hashmap_rehash1.png" style="width:80%"/>
  <img src="/images/hashmap_rehash2.png" style="width:80%"/>
</div>

---

# Industrial Implementation

 <logos-java/> HashMap

-   HashMap for HashSet: HashSet&#60;E&#62; → HashMap&#60;E, Object&#62;
    -   <span class="norm">{e1, e2, e3, ...} → (e1, PRESENT), (e2, PRESENT), (e3, PRESENT), ... </span>

<br/>

<span class="norm">👉 source code: [https://github.com/frohoff/jdk8u-jdk/blob/master/src/share/classes/java/util/HashMap.java](https://github.com/frohoff/jdk8u-jdk/blob/master/src/share/classes/java/util/HashMap.java)</span>


<!--

We dont have another section to study Set data structure, as it can be converted from Map/HashTable. Map/HashTable can be converted from Set also. 

-->

---
layout: center
---

# Skip List

---

# Skip List

<div class="inline-grid grid-cols-[2fr,5fr] gap-4">

  <div align="right">1 Level:</div>
  <div><img src="/images/skip1.webp" style="width:50%"/></div>

  <div align="right">2 Levels:</div>
  <div><img src="/images/skip2.webp" style="width:50%"/></div>

  <div align="right">3 Levels:</div>
  <div><img src="/images/skip3.webp" style="width:50%"/></div>

</div>

<!--
sorted linked list for sorted map
-->

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3><logos-jupyter /> search key</h3>
  </div>
  <div>
    <br/>
    <img src="/images/skip_search.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3><logos-jupyter /> delete key</h3>
  </div>
  <div>
    <br/>
    <img src="/images/skip_del.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3><logos-jupyter /> insert key</h3>
  </div>
  <div>
    <br/>
    <img src="/images/skip_add1.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <h3><logos-jupyter /> insert key</h3>
  </div>
  <div>
    <br/>
    <img src="/images/skip_add2.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List

<br/>

<div class="inline-grid grid-cols-[2fr,3fr] gap-8">

  <div class="norm">
    <p>
    Skip List node with an array of pointers: position pointers[0] stores a level 0 pointer, position pointers[1] stores a level 1 pointer, and so on. <br/> <br/>
    When inserting a new value, the levels (depth) for the new node is randomized.    
    </p>
  </div>
  <div>
    <br/>
    <img src="/images/skip_pointers.png" style="width:70%"/>
  </div>

</div>

---

# Skip List Complexity

<br/>

<div style="width: 50%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="60%">Time Complexity avg</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN) 👈</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
      </tr>
    </tbody>
  </table>
</div>

<br/>

[Skip Lists: A Probabilistic Alternative to Balanced Trees](https://15721.courses.cs.cmu.edu/spring2018/papers/08-oltpindexes1/pugh-skiplists-cacm1990.pdf), William Pugh, 1990

<!--
Insert & Delete need to update the searching path, so it depends on Search. 
-->

--- 

# Skip List vs. Hash Table, Balanced Tree

- keys in order, better for range search   
- operations (linkedlist operations+) simpler than balanced tree (AVL, Red Black Tree, etc.)   
- for Skip List node, avg no. of pointers $\frac{p}{1-p}$, when $p = \frac{1}{4}$, 1.33 < 2 
- single key search, Hash Table close to O(1)
- Skip List implementation simpler 

---
layout: center
---

# Binary Search Tree

---
layout: two-cols
---

# Binary Search Tree (BST)

<br/>

<span class="hl-bg">Binary Search Tree</span> (BST) is a binary tree and:

-   left subtree has smaller elements
-   right subtree has bigger elements

<br/>
   
💡 any BST subtree is still a BST   
💡 BST node must be comparable

<br/>

<span class="norm">💬 in some BST implementation all values are unique, so we exclude duplicates now</span>

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/binary_search_tree1.png" style="width:70%"/>
</div>

<!--
- Linear Search  
- Binary Search  
-->

---

# BST: Operations

<logos-jupyter />

-   search()
-   insert()
-   delete()
-   first()
-   last()
-   before()
-   after()
-   is_empty()

<span class="norm">👉 [https://www.cs.usfca.edu/~galles/visualization/BST.html](https://www.cs.usfca.edu/~galles/visualization/BST.html)</span>

<span class="norm">💬 1962, Hibbard Deletion</span>

---

# BST: Hibbard Deletion

<logos-jupyter /> 


- del min 

- del max 


---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div align="center">
  <img src="/images/hibbard.png" style="width:80%"/>
</div>

::right::

<br/>
<br/>
<br/>
<br/>


<div class="inline-grid grid-cols-[4fr,1fr,4fr] gap-2">
  <div>
    <img src="/images/binary_search_tree1.png"/>
  </div>
  <div style="color: green; text-align: center;">
    <br/><br/>
    <mdi-arrow-right-bold/> <br/>
    <span class="norm">del 10</span>
  </div>
  <div>
    <img src="/images/binary_search_tree2.png"/>
  </div>
</div>

---
layout: two-cols
---

# BST: Hibbard Deletion

<br/>

<div align="center">
  <img src="/images/hibbard.png" style="width:80%"/>
</div>

::right::

<br/>
<br/>
<br/>
<br/>


<div class="inline-grid grid-cols-[4fr,1fr,4fr] gap-2">
  <div>
    <img src="/images/binary_search_tree2.png"/>
  </div>
  <div style="color: green; text-align: center;">
    <br/><br/>
    <mdi-arrow-right-bold/> <br/>
    <span class="norm">del 77</span>
  </div>
  <div>
    <img src="/images/binary_search_tree3.png"/>
  </div>
</div>

---

# BST: Traversal    

- pre-order
- in-order: sorted list   
- post-order   
- level order 

<!--

pre/in/post depends on when we want to proces the node, e.g. for memory management in C++, we probably want to do GC for the node when GC is done for left & right subtree, so post-order may be a choice.  

min, max  
floor, ceil  
rank, select 


-->

---

# Binary Search Tree Complexity

<br/>

<div style="width: 60%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="40%">Operation</th>
        <th id="" width="30%">avg case</th>
        <th id="" width="30%">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---

# When & Where 

<br/>

Binary Search Tree (BST) is used: 

-   implementation of <span class="hl-bg">AVL Tree</span> <span class="hl-bg">Red Black Tree</span> etc.

-   syntax trees used by compiler and calculator

-   <span class="hl-bg">Treap</span> - a probabilistic data structure

-   ...

---
layout: two-cols
---

# Heap vs. BST

<br/>

-   Heap is <span class="uline">balanced</span> tree, BST is not

-   Heap allows duplicates, BST doesnot

-   BST is ordered data structure, Heap is not

-   worst case for building $n$ nodes of BST $O(n \cdot log(n))$, Heap is $O(n)$

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/binary_search_tree4.png" style="width:40%"/>
</div>

--- 
layout: center
---

# AVL 

---
layout: two-cols
---

# AVL

<br/>

-   named after inventors G.M. <span class="hl-color">A</span>del’son-<span class="hl-color">V</span>el’skii and E.M. <span class="hl-color">L</span>andis, 1962

-   first type of <span class="hl-bg">Balanced Binary Search Tree</span> (BBST)

-   height balanced: $BF$ - balance factor  
    $BF = H(node.right) - H(node.left)$   
    $BF \in {-1, 0, 1}$

-   heigh and no. of nodes: $O(logN)$ 

<br/>

- <span class="norm">perfect binary tree (minimum heigh)</span> 
- <span class="norm">complete binary tree</span> 
- <span class="norm">Binary Heap, Red Black Tree, Segment Tree</span> 

::right::

<br/>

<br/>

<br/>

<br/>

<div align="center">
  <img src="/images/avl1.png" style="width:70%"/>
</div>

<!--

The example is a binary search tree, not complete binary tree, but it is balanced. 

-->

---

# AVL Rebalance

<br/>

TBD

---

# BST & AVL Complexity

<br/>

<div style="width: 80%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Operation</th>
        <th id="">BST avg</th>
        <th id="">BST worst</th>
        <th id="">AVL avg</th>
        <th id="">AVL worst</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Search</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
      <tr class="even">
        <th>Insert</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
      <tr class="odd">
        <th>Delete</th>
        <td>O(logN)</td>
        <td>O(N)</td>
        <td>O(logN)</td>
        <td>O(logN)</td>
      </tr>
    </tbody>
  </table>
</div>

--- 
layout: center
---

# Red Black Tree

---

# Red Black Tree

<br/>

TBD

--- 
layout: center
---

# Segment Tree

---

# Segment Tree

<br/>

TBD

--- 
layout: center
---

# B Tree

---

# B Tree

<br/>

TBD

--- 
layout: center
---

# B+ Tree

---

# B+ Tree

<br/>

TBD

--- 
layout: center
---

# Trie 


---

# Trie

<br/>

TBD

---
layout: center
---

# Sorting

---

# Sorting

<br/>

-   make data in order
-   different **Algorithmic Thinking**

---

# Sorting: Selection

<logos-jupyter />

<br/>

- sort the arr from left to right 
- every time select the smallest 
- for position i: 
  - [0, i) sorted
  - [i,n) unsorted 
  - find the smallest from arr[i, n) and place at arr[i]

<br/>

<img src="/images/sort_selection.gif" style="width:50%"/>

---

# Sorting: Insertion

<logos-jupyter />

<br/>

- sort the arr from left to right 
- for postion i:
  - [0, i) sorted
  - [i, n) unsorted
  - insert arr[i] to the proper position on the left 

<br/>

<img src="/images/sort_insertion.gif" style="height:50%"/>

---

# Sorting: Bubble

<logos-jupyter />

<br/>

- sort the arr from right to left
- for postion postion n-i-1
  - [n-i, n) sorted
  - [0, n-i-1) unsorted
  - bubble the biggest to arr[n-i-1]

<br/>

<img src="/images/sort_bubble.gif" style="width:50%"/>

---

# Sorting: Merge 

John von Neumann

<logos-jupyter />

- recursively [l, m, r]: 
  - sort [l, m]
  - sort [m+1, r]
  - merge two sorted array [l, m] & [m+1, r]

<br/>

<div class="inline-grid grid-cols-[1fr,3fr] gap-8">
  <div>
    <img src="/images/JohnvonNeumann.jpeg" style="height:50%"/>
  </div>
  <div>
    <img src="/images/sort_merge.gif" style="height:60%"/>
  </div>
</div>


<!--
John von Neumann
-->

---
layout: two-cols
---

# Sorting: Merge

<br/>

- Time Complexity $O(n \cdot log_2n)$
- Space Complexity $O(n)$

<span class="norm">at each level i = $0,1,2, ..., log_2n$</span>   
<span class="norm">there are $2^i$ subproblems, each of size $\frac{n}{2^i}$</span>  
<span class="norm">total # of operations at level i $\le 2^i \cdot c(\frac{n}{2^i}) = c \cdot n$ </span>  
<span class="norm">complexity on each level is $O(n)$</span>  

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

"recursion tree"

<div align="left">
  <img src="/images/sort_merge_complexity.png" style="width:80%"/>
</div>


<!-- 
Analysis of Algorithms:  

- worst case
- ignore constant factors, lower-order terms  
- asymptotic analysis (large input size) 

Algo analysis: lose a little bit of granularity of information but we dont lose what we really care about which is accurate guidence about what algorithms are gonna be faster than the others. 
-->

---

# Sorting: Merge

<logos-jupyter />

<br/>

- merge top down:
  - <span class="norm">[On finding the average of two unsigned integers without overflow](https://devblogs.microsoft.com/oldnewthing/20220207-00/?p=106223)</span> 
  - insertion 
  - tmp 

- merge buttom up  

- worst case: 
    - <span class="norm">sorted array</span>
    - <span class="norm">sorted array (reversed order)</span>
    - <span class="norm">duplicates</span>

---

# Sorting: Quick 

Tony Hoare

<logos-jupyter /> 

- partition: select v, so that [l, p-1] smaller than v and [p+1, r] bigger than v 
- recursive sort [l, p-1]
- recursive sort [p+1, r]

<br/>

<div class="inline-grid grid-cols-[1fr,3fr] gap-8">
  <div>
    <img src="/images/TonyHoare.jpeg" style="height:85%"/>
  </div>
  <div>
    <img src="/images/sort_quick.gif"/>
  </div>
</div>

<!-- 
Tony Hoare

Quick is faster than Merge because partion func is faster than merge function
-->

---

# Sorting: Quick 

<br/>

- worst case: $O(n^2)$
    - <span class="norm">sorted array</span>
    - <span class="norm">sorted array (reversed order)</span>
    - <span class="norm">duplicates</span>
    - $O(n^2)$ possibility: $\frac{1}{n} * \frac{1}{n-1} * \frac{1}{n-2} * ... = \frac{1}{n!}$

- recusion stack overflow 

- random algorithm, time complexity $O(n \cdot log_2n)$ 👉 [Introduction to Algorithms]()

- two-way quicksort, [3-way radix quicksort ](https://en.wikipedia.org/wiki/Multi-key_quicksort), [dual pivot quicksort](https://arxiv.org/abs/1503.08498)

---
layout: two-cols
---

# Sorting

<br/>

Simple Sort:  
-   Selection    
-   Insertion
-   Bubble

::right::

<br/>

<br/>

<br/>

<br/>

Efficient Sort:
-   Heap
-   Merge
-   Quick

<!--
- element comparable
- optimize
- simple sorts vs efficient sorts   
- stability 
-->

---

# Sorting: Complexity

<br/>

<div style="width:100%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">sorting</th>
        <th id="">avg</th>
        <th id="" width="25%">best</th>
        <th id="">worst</th>
        <th id="">inplacement</th>
        <th id="">space</th>
        <th id="">stability</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Selection</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>    
      <tr class="even">
        <th>Insertion</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n) 👍</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="odd">
        <th>Bubble</th>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td>O(n)<sup>*</sup></td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="even">
        <th>Heap</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>         
      <tr class="odd">
        <th>Merge</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n) → O(n)<sup>*</sup></td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td><span class="norm">OUT-place</span></td>
        <td>O(n) 👎</td>
        <td><span class="norm">stable</span></td>
      </tr>
      <tr class="even">
        <th>Quick</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n) → O(n)<sup>*</sup></td>
        <td>O(n<sup><span class="norm">2</span></sup>) 👈</td>
        <td><span class="norm">in-place</span></td>
        <td>O(1)</td>
        <td><span class="norm">NOT stable</span></td>
      </tr>     
    </tbody>
  </table>
</div>

---

# Sorting

<br/>

<div style="width: 80%">
  <table class="ops">
    <thead>
      <tr>
        <th id="" width="30%"> </th>
        <th id="" width="30%">n<sup><span class="norm">2</span></sup></th>
        <th id="" width="20%">n<sub><span class="norm">log</span></sub>n</th>
        <th id="" width="20%">faster</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>n = 10</th>
        <td>100</td>
        <td>33</td>
        <td>3</td>
      </tr>    
      <tr class="even">
        <th>n = 100</th>
        <td>10,000</td>
        <td>664</td>
        <td>15</td>
      </tr>   
      <tr class="odd">
        <th>n = 1,000</th>
        <td>1,000,000</td>
        <td>9,966</td>
        <td>100</td>
      </tr>    
      <tr class="even">
        <th>n = 10,000</th>
        <td>100,000,000</td>
        <td>132,877</td>
        <td>753</td>
      </tr>    
    </tbody>
  </table>
</div>

<br/>

👉 <span class="norm"><span class="hl-color">1hr</span> vs.  <span class="hl-color">31days</span> (≈ 753hrs)</span>

---

# Sorting: stability 

<br/>

Stable sort algorithms sort equal elements in the same order that they appear in the input:

<br/>

<div align="center">
  <img src="/images/sort_stability.png" style="width: 20%"/>
</div>


---

# Sorting

<br/>

<div align="center">
  <img src="/images/sorting_algos.png" style="width: 70%"/>
</div>

---
layout: two-cols
---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

[Timsort](https://bugs.python.org/file4451/timsort.txt)

<div style="width:90%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">sorting</th>
        <th id="">best</th>
        <th id="">avg</th>
        <th id="">worst</th>
      </tr>
    </thead>
    <tbody>
      <tr class="even">
        <th>Merge</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
      </tr>
      <tr class="odd">
        <th>Quick</th>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sup><span class="norm">2</span></sup>)</td>
      </tr>
      <tr class="even">
        <th class="hl-color">Timsort</th>
        <td>O(n) 👈</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
        <td>O(n<sub><span class="norm">log</span></sub>n)</td>
      </tr>        
    </tbody>
  </table>
</div>

<br/>

- <span class="norm">size < 64, insertion sort</span> 
- <span class="norm">"adaptive merge sort"</span>

::right::

<br/>

<br/>

<br/>

<br/>

sort operations: 

1. <span class="norm">moving or coping objects (just one step)</span>
2. <span class="norm">comparing two objects:</span>   
    <span class="norm">compare class type → compare method → if not, ...</span>

<br/>

> <span class="norm"> comparing objects is very expensive</span>

---

# Industrial Implementation

<logos-python/> list.sort() or sorted(list)

- run: parts that are strictly increasing (if decreasing, reverse it)
- split into multiple runs 
- merge runs - **Galloping**: 

[1, 2, 3, ..., 100, ..., 101, 102, 103, ..., 200]  
run1 = [1, 2, 3, , ..., 100]  
run2 = [101, 102, 103, , ..., 200]  

$run2[2^{n-1} - 1] < run1[0] \leq run2[2^n - 1]$   
binary search: $O(N)$ → $O(logN)$

<style>
p {
    font-family: "Open Sans";
    font-size: 0.8rem;
}
</style>
---

# Industrial Implementation

 <logos-java/> Arrays.sort() or Collections.sort()

- primitive array: **Dual Pivot Quicksort**  

- object array: **Timsort**

---
layout: center
---

# Selection

---

# Selection

<br/>

In computer science, a <span class="hl-color">selection algorithm</span> is an algorithm for finding the k<sup>th</sup> smallest number in a list or array; such a number is called the k<sup>th</sup> order statistic. This includes the cases of finding the minimum, maximum, and median elements. 

---

# Prune-and-Search

<br/>

TBD

---

# Randomised Quick Sort

<br/>

TBD

---
layout: center
---

# Text Processing

---

# Brute Force

<br/>

TBD

---

# Boyer-Moore

<br/>

TBD

---

# Knuth-Morris-Pratt (KMP)

<br/>

TBD

---
layout: center
---

# Dynamic Programming (DP)

---
layout: center
---

# Graph

---

# Graph Terminology

<br/>

TBD

---

# Depth-First Search (DFS)

<br/>

TBD

---

# Breadth-First Search (BFS)

<br/>

TBD

---

# Dijkstra's Shortest Path

<br/>

TBD

---

# Min-Spanning Tree (MST)

<br/>

TBD

---

# Prim-Jarnik Algorithm

<br/>

TBD

---

# Kruskal's Algorithm

<br/>

TBD

---

# DAG

<br/>

TBD

---

<div id="labs">
</div>

<style>

#labs {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: url('/images/lab.jpg');
  background-repeat: no-repeat;
  background-size: cover;
}

</style>

---

# Lab 1

<br/>

TBD

---

# Lab 2

<br/>

TBD

---

# Lab 3

<br/>

v

---

# Lab 4

<br/>

TBD

---

# Lab 5

<br/>

TBD

---

# Lab 6

<br/>

TMA review