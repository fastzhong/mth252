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
        <li>Sorting: <span class="hl-bg">Merge-Sort</span>, <span class="hl-bg">Quick Sort</span> <br/> Selection: <span class="hl-bg">Binary Search</span>, <span class="hl-bg">Prune-and-Search</span>, <span class="hl-bg">Randomized-Quicksort</span></li> 
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


<span class="norm">👉 MTH252 is much more difficult than MTH251</span>

---

# Slides & Notebooks

<br/>

slides online: [https://mth252.fastzhong.com/](https://mth252.fastzhong.com/)

<mdi-file-pdf /> [https://mth252.fastzhong.com/mth252.pdf](https://mth251.fastzhong.com/mth252.pdf)

<logos-github-octocat /> labs: [https://github.com/fastzhong/mth252/tree/main/public/notebooks](https://github.com/fastzhong/mth252/tree/main/public/notebooks)

<br/>

<br/>

👉 Python & Big O review:  [MTH251 lab1](https://mth252.fastzhong.com/) 

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

[<mdi-file-code /> Leetcode](https://leetcode.com/)

<img src="/images/leetcode.png" style="border-radius: 8px; width: 70%"/>

<p class="norm">
🏃‍♂️ learning by doing, implementing the algo from scratch  <br/>
🙇🏻‍♂️ problem solving 
</p>

---

# Learning Resource

📚 books

if you want to dive deeper into proofs and the mathematics of computer science:

[Building Blocks for Theoretical Computer Science](https://mfleck.cs.illinois.edu/building-blocks/index-sp2020.html) by Margaret M. Fleck

---

# Priority Queue

-   FIFO/LILO
-   <span class="hl">each element (k, v) has a certain priority k and k must be compariable</span>
-   min priority queue (smaller k, higher priority)
-   max priority queue (bigger k, higher priority)

e.g. printer queue, cpu task scheduler, etc.

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
        <th id="">Priority Queue</th>
        <th id="">unsorted list</th>
        <th id="">sorted list</th>
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

# Binary Heap

<br/>

-   <span class="hl">Complete Binary Tree</span>

-   k value for any node in the tree <span class="hl">smaller than any child node</span>

<img src="/images/binary_heap.png" style="width: 80%"/>

<br/>

<span class="norm">👉 A complete binary tree is a tree in which at every level, except possibly the last is completely filled and all the nodes are as far left as possible.
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

👉 [https://www.cs.usfca.edu/~galles/visualization/Heap.html](https://www.cs.usfca.edu/~galles/visualization/Heap.html)

---

# Priority Queue Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Priority Queue</th>
        <th id="">unsorted list</th>
        <th id="">sorted list</th>
        <th id="">binary heap</th>
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

# When & Where is a Priority Queue (PQ) used?

<br/>

-   used in certain implementations of <span class="hl-bg">Dijkstra's Shortest Path</span> algorithm

-   <span class="hl-bg">Best First Search</span> (BFS) algorithms such as A\* uses PQ to continuously grab the next most promising node

-   used in <span class="hl-bg">Huffman coding</span> (which is often used for lossless data compression)

-   used by <span class="hl-bg">Minimum Spanning Tree</span> (MST) algorithms

-   anytime you need to dynamically fetch the "next best" or "next worst" element

- ...

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

# Heapify

<logos-jupyter />

<br/>

<span class="hl">Heapify</span>: convert the array to be a binary heap (array)

by "sift down" the non-leaf node one by one from bottom to top

time complexity: $O(N)$  
space complexity: $O(1)$

<!--
last non-leaf node: parent of last leaf node
-->

---
layout: two-cols
---

# Heapify

<br/>

Complete Binary Tree (Perfect Binary Tree)

|                       |                     |            |           |
| --------------------: | :------------------ | ---------: | :---------|
|     last level nodes: | $\frac{n}{2}$       | sift_down: | $\frac{n}{2} * 0$ |
| 2nd last level nodes: | $\frac{n}{4}$       | sift_down: | $\frac{n}{4} * 1$ |
|                   ... |                     |        ... |           |
| h+1 last level nodes: | $\frac{n}{2^(h+1)}$ | sift_down: | $\frac{n}{2^(h+1)} \cdot h$ |


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
    font-size: 0.8rem;
}
</style>

---

# Heap Sort

<br/>

<img src="/images/heap_sort.png" style="height: 85%"/>

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

    -   loop through the list until find the element with key k

-   set(k,v)

    -   create a new node (k,v) and add it at the front

-   delete(k)
    -   loop through the list until find the element with key k
    -   remove it by updating the pre and next elements

👉 Complexity: $O(n)$

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

-   MAD:  $(a\;\cdot\;i + b)\;mod\;p$  
    where $p$ is a prime number, $p > N$, $a$ and $b$ are random number, $a\in[0, p-1]$, $b\in[0, p-1]$

<br/>

👉 <span class="norm">[good hash table primes](https://planetmath.org/goodhashtableprimes) </span>

---
layout: two-cols
---

# Hash Function: Collision

<br/>

### chaining (open hashing)

-   one element $O(1)$

-   **linked list** (Java: more than one element) $O(1) + O(n)$

-   **treemap/red black tree** (Java: more than 8 elements) $O(1) + O(logN)$

::right::

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

<span class="norm">💡 coding tips:</span>
-   <span class="norm">avoid to use real or big number as key (e.g. $H(0.0) == H(-0.0)$) </span> 
-   <span class="norm">compare hash code first, before compare x and y</span>  
-   <span class="norm">overwrite either both of **eq** and **hash** or neither of them</span>  

<br/>

> Designing good hash functions requires a blending of sophisticated mathematics and clever engineering

::right::

<br/>

```python
class UserGroup:

  def __init__(self, name, city, status):
    self.name = name
    self.city = city
    self.status = status

  def __hash__(self):
    result = 17
    result = 31 * result + hash(name)
    if not city:
      result = 31 * result + hash(city)
    return result

  def __eq__(self, other):
    if isinstance(other, UserGroup):
      return self.__hash__() == other.__hash__()
    if self.status == other.status:
      return True
    return False
```

---

# Map/Hash Table Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Hash Table</th>
        <th id="">best case</th>
        <th id="">avg case</th>
        <th id="">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Searching</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insertion</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Deletion</th>
        <td>O(1)</td>
        <td>O(1)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---

# Skip List

<div class="inline-grid grid-cols-[2fr,5fr] gap-4">

  <div align="right">Level 0:</div>
  <div><img src="/images/skip1.webp" style="width:50%"/></div>

  <div align="right">Level 1:</div>
  <div><img src="/images/skip2.webp" style="width:50%"/></div>

  <div align="right">Level 2:</div>
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
    <h3><logos-jupyter /> add key</h3>
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
    <h3><logos-jupyter /> add key</h3>
  </div>
  <div>
    <br/>
    <img src="/images/skip_add2.webp" style="width:70%"/>
  </div>

</div>

---

# Skip List Complexity

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Skip List</th>
        <th id="">Time Complexity</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Searching</th>
        <td>O(logN)</td>
      </tr>
      <tr class="even">
        <th>Insertion</th>
        <td>O(logN)</td>
      </tr>
      <tr class="odd">
        <th>Deletion</th>
        <td>O(logN)</td>
      </tr>
    </tbody>
  </table>
</div>

---
layout: two-cols
---

# Binary Search Tree 

<br/>

<span class="hl-bg">Binary Search Tree</span> (BST) is a binary tree and: 

- left subtree has smaller elements
- right subtree has bigger elements 

   
💡 any BST subtree is still a BST   
💡 BST node must be comparable  


<br/>

<span class="norm">💬  in some BST implementation all values are unique, so we exclude duplicates now</span>

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/binary_search_tree1.png" style="width:70%"/>

---

# Binary Search Tree: Operations

<logos-jupyter />

- search()
- insert()
- delete()
- first()
- last()
- before(p)
- after(p)
- is_empty()

👉 [https://www.cs.usfca.edu/~galles/visualization/BST.html](https://www.cs.usfca.edu/~galles/visualization/BST.html)

---
layout: two-cols
---
# Binary Search Tree: Operations

<logos-jupyter />

💬 1962, Hibbard Deletion

```python
# 

```

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/binary_search_tree2.png" style="width:70%"/>


---
layout: two-cols
---
# Binary Search Tree: Operations

<logos-jupyter />

💬 1962, Hibbard Deletion

```python
# 

```

::right::

<br/>

<br/>

<br/>

<br/>

<br/>

<img src="/images/binary_search_tree3.png" style="width:70%"/>

---

# Binary Search Tree Complexity 

<br/>

<div style="width: 70%">
  <table class="ops">
    <thead>
      <tr>
        <th id="">Binary Search Tree</th>
        <th id="">avg case</th>
        <th id="">worst case</th>
      </tr>
    </thead>
    <tbody>
      <tr class="odd">
        <th>Searching</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="even">
        <th>Insertion</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
      <tr class="odd">
        <th>Deletion</th>
        <td>O(logN)</td>
        <td>O(n)</td>
      </tr>
    </tbody>
  </table>
</div>

---

# When & Where is a Binary Search Tree (BST) used?

<br/>

-   implementation of <span class="hl-bg">AVL Tree</span> <span class="hl-bg">Red Black Tree</span> etc. 

-   syntax trees used by compiler and calculator 

-   <span class="hl-bg">Treap</span> - a probabilistic data structure

- ...

---


# AVL

<br/>

named after their two inventors G.M. Adel’son-Vel’skii and E.M. Landis

---

# Red Black Tree

<br/>

blablablan

---

# Sorting

---

# Merge-Sort

<br/>

blablablan

---

# Quick Sort

<br/>

blablablan

---

# Text Pattern Matching

<br/>

blablablan

---

# Brute Force

<br/>

blablablan

---

# Boyer-Moore

<br/>

blablablan

---

# Knuth-Morris-Pratt (KMP)

<br/>

blablablan

---

# Graph

---

# Depth-First Search (DFS)

<br/>

blablablan

---

# Breadth-First Search (BFS)

<br/>

blablablan

---

# Dijkstra's Shortest Path

<br/>

blablablan

---

# Min-Spanning Tree (MST)

<br/>

blablablan

---

# DAG

<br/>

blablablan

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

blablablan

---

# Lab 2

<br/>

blablablan

---

# Lab 3

<br/>

blablablan

---

# Lab 4

<br/>

blablablan

---

# Lab 5

<br/>

blablablan

---

# Lab 6

<br/>

blablablan
