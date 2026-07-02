# 🎯 LeetCode 55 — Jump Game

<p align="center">

<img src="https://img.shields.io/badge/Language-Python-3776AB?style=for-the-badge&logo=python&logoColor=white">

<img src="https://img.shields.io/badge/Difficulty-Medium-orange?style=for-the-badge">

<img src="https://img.shields.io/badge/Pattern-Greedy-success?style=for-the-badge">

<img src="https://img.shields.io/badge/Status-Solved-brightgreen?style=for-the-badge">

</p>

---

# 📖 Problem Statement

You are given an integer array `nums`, where each element represents your **maximum jump length** from that position.

Return **True** if you can reach the last index, otherwise return **False**.

---

# 🧠 Pattern Used

* Greedy
* Array

---

# 💡 Intuition

Instead of trying every possible jump, keep track of the **farthest index** that can be reached.

If the current index is ever greater than the farthest reachable index, the last index is impossible to reach.

---

# 🚀 Key Insight

At every position:

```text
Reach = Current Index + Jump Length
```

Update the maximum reachable index:

```text
farthest = max(farthest, i + nums[i])
```

If:

```text
i > farthest
```

the current position is unreachable, so return **False** immediately.

---

# 🏗️ Example

Input

```text
nums = [2,3,1,1,4]
```

Traversal

```text
Index :      0   1   2   3   4
Value :      2   3   1   1   4
Reach :      2   4   3   4   8

Farthest:
0 → 2 → 4 → 4 → 8
```

Output

```text
True
```

---

# ❌ Failure Example

Input

```text
nums = [3,2,1,0,4]
```

Traversal

```text
Index :      0   1   2   3   4
Value :      3   2   1   0   4
Reach :      3   3   3   3   X
```

At index **4**

```text
4 > farthest (3)
```

The last index cannot be reached.

Output

```text
False
```

---

# ⚙️ Algorithm

```text
Initialize farthest = 0

Traverse the array

    If current index > farthest
        Return False

    Update farthest

Return True
```

---

# 💻 Python Solution

```python
class Solution(object):
    def canJump(self, nums):

        farthest = 0

        for i in range(len(nums)):

            if i > farthest:
                return False

            farthest = max(farthest, i + nums[i])

        return True
```

---

# 📊 Complexity Analysis

| Operation        | Complexity |
| ---------------- | ---------: |
| Traversal        |       O(n) |
| Time Complexity  |   **O(n)** |
| Space Complexity |   **O(1)** |

---

# 🎯 Key Learning

* ✅ Learned the Greedy algorithm pattern.
* ✅ Tracked the farthest reachable index efficiently.
* ✅ Avoided unnecessary recursive or dynamic programming solutions.
* ✅ Solved the problem in linear time with constant extra space.
* ✅ Strengthened understanding of reachability problems.

---

# 🔗 Related Problems

* Jump Game II
* Gas Station
* Partition Labels
* Trapping Rain Water
* Container With Most Water

---

# ⭐ Conclusion

Jump Game is a classic Greedy problem that demonstrates how maintaining the **maximum reachable index** is enough to determine whether the destination can be reached. Instead of exploring every possible jump, the algorithm continuously expands the reachable range, achieving an optimal **O(n)** solution with **O(1)** extra space.
