# 🪟 Sliding Window Technique

A powerful optimization technique used to solve problems involving **subarrays / substrings** in **O(n)** time.

---

## 📌 What is Sliding Window?

Sliding Window is a method where we maintain a **window (range of elements)** and move it across the array instead of recalculating values repeatedly.

👉 Instead of checking all subarrays (**O(n²)**), we:

* Expand the window → add new elements
* Shrink the window → remove old elements

---

## ⚙️ Types of Sliding Window

### 🔹 1. Fixed Size Window

* Window size remains constant (`k`)

#### ✅ Example:

**Maximum sum of subarray of size k**

```cpp
int windowSum = 0;

// first window
for(int i = 0; i < k; i++) {
    windowSum += arr[i];
}

for(int i = k; i < n; i++) {
    windowSum += arr[i];        // add next element
    windowSum -= arr[i - k];    // remove previous element
}
```

---

### 🔹 2. Variable Size Window

* Window size changes based on condition

#### ✅ Example:

**Smallest subarray with sum ≥ k**

```cpp
int left = 0, sum = 0;

for(int right = 0; right < n; right++) {
    sum += arr[right];

    while(sum >= k) {
        // process answer
        sum -= arr[left];
        left++;
    }
}
```

---

## 🔍 How to Identify Sliding Window?

Use Sliding Window when:

### ✅ 1. Problem involves:

* Subarrays / Substrings
* Contiguous elements

---

### ✅ 2. Keywords:

* "longest"
* "shortest"
* "maximum / minimum"
* "count subarrays"

---

### ✅ 3. Constraints:

* Large input size (n ≥ 10⁵)
* Brute force O(n²) not feasible

---

### ✅ 4. Conditions:

* sum ≤ k
* sum ≥ k
* at most k distinct elements
* exactly k distinct elements

---

## ⚠️ When NOT to Use Sliding Window

❌ Negative numbers in sum problems → use Prefix Sum
❌ Non-contiguous problems → use DP / Hashing

---

## ⚡ Sliding Window Template

```cpp
int left = 0;

for(int right = 0; right < n; right++) {

    // include current element
    // update state

    while(condition breaks) {
        // remove left element
        left++;
    }

    // update answer
}
```

---

## 🚀 Common Problems

* Longest Substring Without Repeating Characters
* Maximum Sum Subarray of Size K
* Minimum Window Substring
* Count Subarrays with Condition

---

## 💡 Quick Summary

| Feature         | Sliding Window                |
| --------------- | ----------------------------- |
| Works on        | Contiguous data               |
| Time Complexity | O(n)                          |
| Window Types    | Fixed / Variable              |
| Best for        | Subarray / Substring problems |

---

## 🔥 Pro Tip

👉 If problem says **"contiguous + optimize" → think Sliding Window first**
