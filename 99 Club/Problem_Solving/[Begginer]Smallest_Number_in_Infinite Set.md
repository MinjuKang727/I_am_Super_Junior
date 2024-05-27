<img src="https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/e0b54a2a-2ee6-41b8-95bb-8f4f71535aa4" align="left" width="10%">

 | 자바 | 비기너
# 🔢 2336. Smallest Number in Infinite Set
`medium`

You have a set which contains all positive integers `[1, 2, 3, 4, 5, ...]`.

Implement the `SmallestInfiniteSet` class:

- `SmallestInfiniteSet()` Initializes the **SmallestInfiniteSet** object to contain **all** positive integers.
- `int popSmallest()` **Removes** and returns the smallest integer contained in the infinite set.
- `void addBack(int num)` **Adds** a positive integer `num` back into the infinite set, if it is **not** already in the infinite set.
 

#### Example 1:
> **Input**  
["SmallestInfiniteSet", "addBack", "popSmallest", "popSmallest", "popSmallest", "addBack", "popSmallest", "popSmallest", "popSmallest"]  
[[], [2], [], [], [], [1], [], [], []]  
**Output**  
[null, null, 1, 2, 3, null, 1, 4, 5]  
> **Explanation**  
SmallestInfiniteSet smallestInfiniteSet = new SmallestInfiniteSet();  
smallestInfiniteSet.addBack(2);    // 2 is already in the set, so no change is made.  
smallestInfiniteSet.popSmallest(); // return 1, since 1 is the smallest number, and remove it from the set.  
smallestInfiniteSet.popSmallest(); // return 2, and remove it from the set.  
smallestInfiniteSet.popSmallest(); // return 3, and remove it from the set.  
smallestInfiniteSet.addBack(1);    // 1 is added back to the set.  
smallestInfiniteSet.popSmallest(); // return 1, since 1 was added back to the set and  
                                   // is the smallest number, and remove it from the set.  
smallestInfiniteSet.popSmallest(); // return 4, and remove it from the set.  
smallestInfiniteSet.popSmallest(); // return 5, and remove it from the set.  
 

#### Constraints:
- `1 <= num <= 1000`
- At most `1000` calls will be made **in total** to `popSmallest` and `addBack`.

Accepted    **134.7K**  |  Submissions    **187.7K**  |  Acceptance Rate    **71.8%**  

🏷 Topics  
`Hash Table` `Design` `Heap (Priority Queue)`  

---

## Solution with PriorityQueue([LeetCode에 Post한 Solution 링크 👉](https://leetcode.com/problems/smallest-number-in-infinite-set/solutions/5209823/solution-with-priorityqueue))
```java
import java.util.PriorityQueue;

class SmallestInfiniteSet {

    PriorityQueue<Integer> pq;
    public SmallestInfiniteSet() {
        pq = new PriorityQueue<>();
        
        for(int i = 1; i <= 1000; i++) {
            pq.offer(i);
        }

    }
    
    public int popSmallest() {

        return pq.poll();
    }
    
    public void addBack(int num) {
       if (!pq.contains(num)){
           pq.offer(num);
       }
       
    }
}

/**
 * Your SmallestInfiniteSet object will be instantiated and called as such:
 * SmallestInfiniteSet obj = new SmallestInfiniteSet();
 * int param_1 = obj.popSmallest();
 * obj.addBack(num);
 */
```
Runtime    **68ms**  |  Memory    **45.79MB**
<details>
  <summary>submission</summary>

  ![image](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/5e912f3b-b310-47bd-9325-0c9277b3e820)
</details>

<br>

## Solution with String([LeetCode에 Post한 Solution 링크 👉](https://leetcode.com/problems/smallest-number-in-infinite-set/solutions/5209927/solution-with-string))
```java
import java.util.Arrays;

class SmallestInfiniteSet {

    String s;

    public SmallestInfiniteSet() {
        s = "0".repeat(1000);

    }
    
    public int popSmallest() {
        int i = s.indexOf("0");

        s = s.substring(0, i) + "1" + s.substring(i + 1);

        return i + 1;
    }
    
    public void addBack(int num) {
       s = s.substring(0, num - 1) + "0" + s.substring(num);
       
    }
}

/**
 * Your SmallestInfiniteSet object will be instantiated and called as such:
 * SmallestInfiniteSet obj = new SmallestInfiniteSet();
 * int param_1 = obj.popSmallest();
 * obj.addBack(num);
 */
```

Runtime    **42ms**  |  Memory    **45.5MB**

<details>
  <summary>Submission</summary>

  ![image](https://github.com/MinjuKang727/I_am_Super_Junior/assets/108849480/10d44421-d2df-4112-9557-167d31a712d3)
</details>
