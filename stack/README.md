# 📚 DSA Preparation – Stack (Top Problems)

Track your progress on **Stack-based problems**.
Update `[ ] → [x]` when completed.

---

## 🚀 Problem Tracker

| Done | #  | Problem                                  | Difficulty | Pattern                    | Link                                                                    | Basic Idea                                      |
| ---- | -- | ---------------------------------------- | ---------- | -------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------- |
| [x]  | 1  | Valid Parentheses                        | Easy       | Stack                      | https://leetcode.com/problems/valid-parentheses/                        | Push opening brackets, match and pop on closing |
| [ ]  | 2  | Min Stack                                | Medium     | Stack Design               | https://leetcode.com/problems/min-stack/                                | Maintain extra stack for min values             |
| [ ]  | 3  | Next Greater Element I                   | Easy       | Monotonic Stack            | https://leetcode.com/problems/next-greater-element-i/                   | Use decreasing stack to find next greater       |
| [ ]  | 4  | Next Greater Element II                  | Medium     | Circular Stack             | https://leetcode.com/problems/next-greater-element-ii/                  | Traverse array twice                            |
| [ ]  | 5  | Daily Temperatures                       | Medium     | Monotonic Stack            | https://leetcode.com/problems/daily-temperatures/                       | Store indices, pop when warmer found            |
| [ ]  | 6  | Remove K Digits                          | Medium     | Greedy + Stack             | https://leetcode.com/problems/remove-k-digits/                          | Remove larger digits to minimize number         |
| [ ]  | 7  | Largest Rectangle in Histogram           | Hard       | Monotonic Stack            | https://leetcode.com/problems/largest-rectangle-in-histogram/           | Find next smaller elements                      |
| [ ]  | 8  | Maximal Rectangle                        | Hard       | Stack + Matrix             | https://leetcode.com/problems/maximal-rectangle/                        | Convert to histogram per row                    |
| [ ]  | 9  | Evaluate Reverse Polish Notation         | Medium     | Stack                      | https://leetcode.com/problems/evaluate-reverse-polish-notation/         | Push numbers, apply operators                   |
| [ ]  | 10 | Basic Calculator                         | Hard       | Stack + Expression Parsing | https://leetcode.com/problems/basic-calculator/                         | Handle parentheses and signs                    |
| [ ]  | 11 | Simplify Path                            | Medium     | Stack                      | https://leetcode.com/problems/simplify-path/                            | Process directories using stack                 |
| [ ]  | 12 | Decode String                            | Medium     | Stack                      | https://leetcode.com/problems/decode-string/                            | Use stack for nested patterns                   |
| [ ]  | 13 | Score of Parentheses                     | Medium     | Stack                      | https://leetcode.com/problems/score-of-parentheses/                     | Track score using stack                         |
| [ ]  | 14 | Asteroid Collision                       | Medium     | Stack Simulation           | https://leetcode.com/problems/asteroid-collision/                       | Simulate collisions using stack                 |
| [ ]  | 15 | Remove All Adjacent Duplicates in String | Easy       | Stack                      | https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/ | Push/pop when duplicate found                   |

---

## 🧠 Stack Template (C#)

```csharp id="c0a7fx"
Stack<int> stack = new Stack<int>();

foreach (var item in arr)
{
    while (stack.Count > 0 && condition)
    {
        stack.Pop();
    }

    stack.Push(item);
}
```

---

## 📊 Progress

Completed: **0 / 15**

---

## 🎯 Key Patterns Covered

* Basic Stack usage
* Monotonic Stack (increasing/decreasing)
* Expression evaluation
* Stack-based simulation
* Histogram problems

---
