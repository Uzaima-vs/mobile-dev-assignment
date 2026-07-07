# Assignment Mobile

> **Fill in the table below before you start.**

| Field | Your Entry |
|---|---|
| **Name** | Uzaima Naeem Awan|
| **Registration Number** | 132261261|
| **Portal ID** | 132261261 |
| **Submission Date** | 9 July 2026 |

---

## 📖 Learn Markdown First

This assignment is a Markdown (`.md`) file. If you are new to Markdown, go through these first:

- 🎥 Video: [Markdown Crash Course](https://www.youtube.com/watch?v=LxeclcePg-c&t=356s)
- 📄 Docs: [GitHub — Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## ✍️ Where to Write

Each problem below has **two empty blocks** for you:

1. **Steps / Flow** — write, in plain English, the steps your solution follows *before* you code. Numbered steps are fine.
2. **Solution (Dart)** — write your algorithm inside the ` ```dart ` code block.

Do **not** change the problem statements, examples, or function signatures. Only fill in your blocks.

## 👀 How to Preview

- **VS Code:** open this file and press `Ctrl+Shift+V` (Windows) / `Cmd+Shift+V` (Mac) to see the rendered preview.
- **Gist:** after pasting your content, the **Preview** tab (next to *Edit new file*) shows how it will render.

## 📤 How to Submit

1. Go to [gist.github.com](https://gist.github.com/) (sign in with your GitHub account).
2. Set the filename to `MOBILE-Assignment.md` — the `.md` extension is required for rendering.
3. Paste the full contents of this file (with your answers filled in).
4. Click **Create public gist**.
5. Copy the gist URL from your browser and submit that link on the portal.

💡 You can test your Dart code online at [dartpad.dev](https://dartpad.dev/) before pasting it in.

---

# Problems

---

## Problem 1 — Even or Odd

Given an integer `n`, return the string `"Even"` if `n` is even, and `"Odd"` if `n` is odd.

**Example 1:**

```
Input: n = 8
Output: "Even"
Explanation: 8 is divisible by 2.
```

**Example 2:**

```
Input: n = 7
Output: "Odd"
Explanation: 7 leaves a remainder of 1 when divided by 2.
```

**Constraints:**

- `-10^9 <= n <= 10^9`

**Function:**

```dart
String checkEvenOdd(int n) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Take Input: Receive the integer n.
Apply Modulo: Compute n % 2 to find the remainder.
Check Remainder: If the remainder is 0, the number is even.
Handle Negative Numbers: Dart's % operator handles negative numbers correctly (-8 % 2 == 0).
Return Result: Return "Even" for true and "Odd" for false.)
```

### 💻 Solution (Dart)

```dart
String checkEvenOdd(int n) {
  // Check if the remainder is 0 when divided by 2
  if (n % 2 == 0) {
    return "Even";
  } else {
    return "Odd";
}

```

---

## Problem 2 — Convert to Parity List

Given an integer list `nums`, replace every **even** number with `0` and every **odd** number with `1`, and return the resulting list.

**Example 1:**

```
Input: nums = [3, 4, 7, 10]
Output: [1, 0, 1, 0]
Explanation: 3 and 7 are odd → 1; 4 and 10 are even → 0.
```

**Example 2:**

```
Input: nums = [2, 2, 5]
Output: [0, 0, 1]
```

**Constraints:**

- `1 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`

**Function:**

```dart
List<int> toParityList(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Output: Create a new list or map the existing list to store the modified values.
Iterate Through List: Loop through each integer num inside the input list nums.
Check Parity: Apply the modulo operator num % 2 to determine if the current number is even or odd.
Transform Values: Replace the number with 0 if it is even, or 1 if it is odd.
Return List: Output the final transformed list of zeros and ones.)
```

### 💻 Solution (Dart)

```dart
List<int> toParityList(List<int> nums) {
  // Use the map function to transform each element and convert it back to a list
  return nums.map((num) => num % 2 == 0 ? 0 : 1).toList();
}

```

---

## Problem 3 — Reverse a List (Without a Stack)

Given an integer list `nums`, return the list in reversed order. You must **not** use a stack and must **not** use the built-in `nums.reversed`. Hint: think of two pointers, one at each end.

**Example 1:**

```
Input: nums = [1, 2, 3, 4, 5]
Output: [5, 4, 3, 2, 1]
```

**Example 2:**

```
Input: nums = [10, 20]
Output: [20, 10]
```

**Constraints:**

- `1 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`
- Do not use a stack or `nums.reversed`.

**Function:**

```dart
List<int> reverseList(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Two Pointers: Set left to index 0 and right to the last index (nums.length - 1).
Loop Until Meet: Run a loop while left is less than right.
Swap Values: Swap the elements at nums[left] and nums[right] using a temporary variable.
Move Pointers: Increment left by 1 and decrement right by 1.
Return List: Return the modified, reversed list)
```

### 💻 Solution (Dart)

```dart
List<int> reverseList(List<int> nums) {
  int left = 0;
  int right = nums.length - 1;
  
  while (left < right) {
    // Temporary storage to hold the left value during the swap
    int temp = nums[left];
    nums[left] = nums[right];
    nums[right] = temp;
    
    // Move pointers closer to the center
    left++;
    right--;
  }
  
  return nums;
}

```

---

## Problem 4 — Reverse a List (Using a Stack)

Given an integer list `nums`, return the list in reversed order **using a stack**. Push every element onto a stack, then pop them one by one — a stack is Last-In-First-Out (LIFO), so popping gives the elements back in reverse. In Dart, use a `List<int>` with only `add()` (push) and `removeLast()` (pop) as your stack.

**Example 1:**

```
Input: nums = [1, 2, 3]
Output: [3, 2, 1]
Explanation: push 1, 2, 3 → pop gives 3, then 2, then 1.
```

**Example 2:**

```
Input: nums = [4, 4, 9, 7]
Output: [7, 9, 4, 4]
```

**Constraints:**

- `1 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`
- You must use a stack (`add`/`removeLast` only). No `reversed`, no index tricks.

**Function:**

```dart
List<int> reverseListWithStack(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Create Stack: Initialize an empty List<int> named stack.
Push Elements: Loop through nums and use stack.add() to push each element.
Create Result: Initialize an empty List<int> named reversedList to store the output.
Pop Elements: Loop while stack is not empty, using stack.removeLast() to get elements in LIFO order.
Add to Result: Use reversedList.add() to collect the popped elements.
Return Result: Return the completed reversedList)
```

### 💻 Solution (Dart)

```dart
List<int> reverseListWithStack(List<int> nums) {
  List<int> stack = [];
  
  // Push all elements from nums into the stack
  for (int num in nums) {
    stack.add(num);
  }
  
  List<int> reversedList = [];
  
  // Pop elements from the stack until it is empty
  while (stack.isNotEmpty) {
    int lastElement = stack.removeLast();
    reversedList.add(lastElement);
  }
  
  return reversedList;
}

```

---

## Problem 5 — Valid Palindrome

Given a string `s`, return `true` if `s` is a **palindrome**, and `false` otherwise. A palindrome reads the same forwards and backwards.

**Example 1:**

```
Input: s = "racecar"
Output: true
Explanation: reversed, "racecar" is still "racecar".
```

**Example 2:**

```
Input: s = "hello"
Output: false
Explanation: reversed, "hello" becomes "olleh".
```

**Constraints:**

- `1 <= s.length <= 10^4`
- `s` consists of lowercase English letters only.

**Function:**

```dart
bool isPalindrome(String s) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Two Pointers: Set left to index 0 and right to the last index (s.length - 1).
Compare Characters: Loop while left is less than right.
Check Mismatch: Compare characters at s[left] and s[right].
Early Exit: If characters do not match, immediately return false.
Advance Pointers: Increment left by 1 and decrement right by 1.
Confirm Palindrome: If the loop completes without mismatches, return true)
```

### 💻 Solution (Dart)

```dart
bool isPalindrome(String s) {
  int left = 0;
  int right = s.length - 1;
  
  while (left < right) {
    // If characters at current pointers don't match, it's not a palindrome
    if (s[left] != s[right]) {
      return false;
    }
    
    // Move pointers toward the center
    left++;
    right--;
  }
  
  return true;
}

```

---

## Problem 6 — Count Occurrences of K

Given an integer list `nums` and an integer `k`, return the number of times `k` appears in `nums`. If `k` does not appear, return `0`.

**Example 1:**

```
Input: nums = [1, 2, 2, 3, 2], k = 2
Output: 3
```

**Example 2:**

```
Input: nums = [5, 6, 7], k = 9
Output: 0
```

**Constraints:**

- `1 <= nums.length <= 10^4`
- `-10^9 <= nums[i], k <= 10^9`

**Function:**

```dart
int countOccurrences(List<int> nums, int k) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Counter: Set a variable count to 0 to keep track of the matches.
Iterate Through List: Loop through each integer num inside the nums list.
Compare with K: Check if the current num is exactly equal to k.
Increment Counter: If they match, increase count by 1.
Return Result: Return the final total count after the loop finishes)
```

### 💻 Solution (Dart)

```dart
int countOccurrences(List<int> nums, int k) {
  int count = 0;
  
  // Iterate through each element in the list
  for (int num in nums) {
    if (num == k) {
      count++;
    }
  }
  
  return count;
}

```

---

## Problem 7 — Frequency of Every Element

Given an integer list `nums`, return a `Map` where each **key** is an element of `nums` and its **value** is the number of times that element appears. Hint: this is Problem 6 for *every* element at once — can you do it in a single pass?

**Example 1:**

```
Input: nums = [1, 2, 2, 3, 3, 3]
Output: {1: 1, 2: 2, 3: 3}
```

**Example 2:**

```
Input: nums = [7, 7, 7]
Output: {7: 3}
```

**Constraints:**

- `1 <= nums.length <= 10^4`
- `-10^9 <= nums[i] <= 10^9`

**Function:**

```dart
Map<int, int> frequencyOfElements(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Map: Create an empty Map<int, int> called frequencies to store number-to-count pairs.
Iterate Through List: Loop through each integer num in the input list nums.
Lookup or Initialize: Use Dart's ?? operator to check if num is already in the map. If it is not, default its current count to 0.
Increment Frequency: Set the value of frequencies[num] to its current count plus 1.
Return Map: Return the populated frequencies map after completing the single pass.)
```

### 💻 Solution (Dart)

```dart
Map<int, int> frequencyOfElements(List<int> nums) {
  Map<int, int> frequencies = {};
  
  // Single pass through the list to populate frequencies
  for (int num in nums) {
    frequencies[num] = (frequencies[num] ?? 0) + 1;
  }
  
  return frequencies;
}

```

---

## Problem 8 — Contains Duplicate

Given an integer list `nums`, return `true` if any value appears **at least twice** in the list, and `false` if every element is distinct. Hint: your answer to Problem 7 already knows this.

**Example 1:**

```
Input: nums = [1, 2, 3, 1]
Output: true
Explanation: 1 appears twice.
```

**Example 2:**

```
Input: nums = [1, 2, 3, 4]
Output: false
Explanation: all elements are distinct.
```

**Constraints:**

- `1 <= nums.length <= 10^5`
- `-10^9 <= nums[i] <= 10^9`

**Function:**

```dart
bool containsDuplicate(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Set: Create an empty Set<int> called seen to store unique numbers.
Iterate Through List: Loop through each integer num in the input list nums.
Check Existence: Check if seen already contains the current num.
Early Exit: If it is already in the set, a duplicate exists; immediately return true.
Add to Set: If it is not in the set, add num to seen and continue.
Return False: If the loop completes without finding duplicates, return false)
```

### 💻 Solution (Dart)

```dart
bool containsDuplicate(List<int> nums) {
  Set<int> seen = {};
  
  // Check each number for duplicates in a single pass
  for (int num in nums) {
    if (seen.contains(num)) {
      return true;
    }
    seen.add(num);
  }
  
  return false;
}

```

---

## Problem 9 — Pair With Sum K

Given an integer list `nums` and an integer `k`, return `true` if there exist **two elements at different positions** whose sum equals `k`, and `false` otherwise.

**Example 1:**

```
Input: nums = [2, 7, 11, 15], k = 9
Output: true
Explanation: nums[0] + nums[1] = 2 + 7 = 9.
```

**Example 2:**

```
Input: nums = [1, 3, 5], k = 10
Output: false
Explanation: no pair adds up to 10. (5 + 5 does not count — 5 appears only once.)
```

**Constraints:**

- `2 <= nums.length <= 10^4`
- `-10^9 <= nums[i], k <= 10^9`
- The two elements must be at different indices.

**Function:**

```dart
bool hasPairWithSum(List<int> nums, int k) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Initialize Complement Set: Create an empty Set<int> called complements to store the target numbers we need.
Iterate Through List: Loop through each integer num inside the input list nums.
Calculate Complement: Find the value needed to reach the target sum (target = k - num).
Check Existence: Check if the complements set already contains this target value.
Early Exit: If found, it means a previous number matches perfectly with the current one to form k; immediately return true.
Track Current Number: If not found, add the current num to the complements set.
Return False: If the loop finishes without finding any matching pair, return false.)
```

### 💻 Solution (Dart)

```dart
bool hasPairWithSum(List<int> nums, int k) {
  Set<int> complements = {};
  
  for (int num in nums) {
    int target = k - num;
    
    // If the complement exists in our set, we found a valid pair
    if (complements.contains(target)) {
      return true;
    }
    
    // Add the current number to the set for future lookups
    complements.add(num);
  }
  
  return false;
}

```

---

## Problem 10 — Remove Duplicates from Sorted List

Given an integer list `nums` sorted in **ascending order**, remove the duplicates **in-place** so that each unique element appears only once. Keep the relative order of the unique elements.

Let `k` be the number of unique elements. After removing duplicates, return `k`. The first `k` elements of `nums` must contain the unique numbers in sorted order — the remaining elements can be ignored.

**Example 1:**

```
Input: nums = [1, 1, 2]
Output: 2, nums = [1, 2, _]
Explanation: there are 2 unique elements; the first 2 slots hold [1, 2]. The rest is ignored.
```

**Example 2:**

```
Input: nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]
Output: 5, nums = [0, 1, 2, 3, 4, _, _, _, _, _]
```

**Constraints:**

- `1 <= nums.length <= 3 * 10^4`
- `-100 <= nums[i] <= 100`
- `nums` is sorted in ascending (non-decreasing) order.
- You must modify `nums` in-place. Do not create a second list.

**Function:**

```dart
int removeDuplicates(List<int> nums) {
  // your code goes below in the Solution block
}
```

### ✏️ Steps / Flow

```
(Handle Base Case: If nums has only 1 element, it is already unique; return 1.
Initialize Unique Pointer: Set a write pointer uniqueIndex to 1 to track where the next unique element belongs.
Iterate Through List: Loop through the list with a read pointer i starting from index 1 to nums.length - 1.
Detect New Unique Element: Compare the current element nums[i] with the previous element nums[i - 1].
Update In-Place: If nums[i] is different from nums[i - 1], assign nums[uniqueIndex] = nums[i] and increment uniqueIndex by 1.
Return Count: Return uniqueIndex as the final count of unique elements)
```

### 💻 Solution (Dart)

```dart
int removeDuplicates(List<int> nums) {
  // If the list is empty or has one element, duplicates are already handled
  if (nums.length <= 1) {
    return nums.length;
  }
  
  // Pointer to track the position of the next unique element
  int uniqueIndex = 1;
  
  // Iterate through the list starting from the second element
  for (int i = 1; i < nums.length; i++) {
    // If the current element is different from the previous one, it's unique
    if (nums[i] != nums[i - 1]) {
      nums[uniqueIndex] = nums[i];
      uniqueIndex++;
    }
  }
  
  return uniqueIndex;
}

```

---

## ✅ Before You Submit — Checklist

- [ ] Name, registration number, and portal ID filled in at the top
- [ ] Steps / Flow written for all 10 problems
- [ ] Dart solution written for all 10 problems
- [ ] File previews correctly (no broken code blocks)
- [ ] Gist created as `MOBILE-Assignment-01.md` and link copied
