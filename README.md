# LEETCODE-BInary_Search-2141
Below is the **full dry run** of the code for:

```
n = 2
batteries = [3, 3, 3]
```

---

# ✅ Step 1 — Pre-processing

```
l = Long.MAX_VALUE
sum = 0
```

Iterating over batteries:

| b | l = min(l, b) | sum += b |
| - | ------------- | -------- |
| 3 | l = 3         | sum = 3  |
| 3 | l = 3         | sum = 6  |
| 3 | l = 3         | sum = 9  |

So after loop:

```
l = 3
sum = 9
r = sum / n = 9 / 2 = 4
result = 0
```

We will binary search mid between **3 and 4**.

---

# ✅ Step 2 — Binary Search

## **Iteration 1**

```
l = 3, r = 4
mid = 3 + (4 - 3) / 2 = 3
```

### Check possible(mid = 3)

```
target = n * mid = 2*3 = 6
```

Now iterate batteries:

| battery | subtract   | target after                   |
| ------- | ---------- | ------------------------------ |
| 3       | min(3,3)=3 | 6 - 3 = 3                      |
| 3       | 3          | 3 - 3 = 0 → <=0 so return true |

possible = **true**

So update:

```
result = 3
l = mid + 1 = 4
```

---

## **Iteration 2**

```
l = 4, r = 4
mid = 4
```

### Check possible(mid = 4)

```
target = n * mid = 2*4 = 8
```

Process batteries:

| battery | subtract   | target after                    |
| ------- | ---------- | ------------------------------- |
| 3       | min(3,4)=3 | 8 - 3 = 5                       |
| 3       | 3          | 5 - 3 = 2                       |
| 3       | 3          | 2 - 3 = -1 → <=0 so return true |

possible = **true**

So update:

```
result = 4
l = mid + 1 = 5
```

---

## Exit loop

Now:

```
l = 5, r = 4 → loop ends
result = 4
```

---

# 🎉 Final Answer

**Maximum run time = 4 units**

---

# ✔ Explanation

For 2 computers and batteries `[3,3,3]`, the maximum equal-running time is **4**, because total energy = **9**, and the optimal distribution can power both computers for 4 time units.

---
