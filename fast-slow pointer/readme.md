# 📊 Prefix Sum Technique

A fundamental technique used to efficiently solve problems involving **range sums** and **subarrays** in **O(n)** time.

---

## 📌 What is Prefix Sum?

Prefix Sum is a method where we precompute cumulative sums so that any subarray sum can be calculated in **O(1)**.

👉 Instead of recalculating sums again and again (**O(n²)**), we store them.

---

## ⚙️ Prefix Sum Formula

```cpp id="t8y2rq"
prefix[i] = prefix[i-1] + arr[i];
```

👉 Subarray sum from index `l` to `r`:

```cpp id="4b7s0h"
sum(l → r) = prefix[r] - prefix[l-1];
```

---

## 🧠 Example

Array:

```
arr = [1, 2, 3, 4]
```

Prefix Array:

```
prefix = [1, 3, 6, 10]
```

👉 Sum from index 1 to 3:

```
= prefix[3] - prefix[0] = 10 - 1 = 9
```

---

## 🔍 How to Identify Prefix Sum?

Use Prefix Sum when:

### ✅ 1. Problem involves:

* Subarrays
* Range sum queries
* Cumulative sums

---

### ✅ 2. Keywords:

* "sum of subarray"
* "range sum"
* "count subarrays"
* "sum equals k"

---

### ✅ 3. Constraints:

* Large input size (n ≥ 10⁵)
* Multiple queries on same array

---

### ✅ 4. Conditions:

* sum = k
* sum divisible by k
* sum in range [L, R]

---

## ⚡ Prefix + HashMap Trick (🔥 Important)

Used in problems like:
👉 Subarray Sum Equals K

```cpp id="9r0r07"
unordered_map<int, int> mp;
mp[0] = 1;

int sum = 0, count = 0;

for(int i = 0; i < n; i++) {
    sum += arr[i];

    if(mp.find(sum - k) != mp.end()) {
        count += mp[sum - k];
    }

    mp[sum]++;
}
```

---

## ⚠️ When NOT to Use Prefix Sum

❌ When problem is not about sum
❌ When sliding window works better (no negatives + fixed conditions)

---

## 🚀 Common Problems

* Subarray Sum Equals K
* Binary Subarrays With Sum
* Range Sum Query
* Subarrays Divisible by K

---

## 💡 Quick Summary

| Feature         | Prefix Sum        |
| --------------- | ----------------- |
| Works on        | Cumulative sums   |
| Time Complexity | O(n)              |
| Best for        | Range sum queries |
| Extra Space     | O(n)              |

---

## 🔥 Pro Tip

👉 If problem says **"subarray sum" → think Prefix Sum + HashMap**
