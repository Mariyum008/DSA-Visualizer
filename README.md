# Block by Block

**Watch data structures and algorithms work one tiny step at a time, explained so simply a 5-year-old could follow.**

Block by Block is an interactive DSA visualizer for engineering students and anyone learning to code. Search a problem, press Play, and watch every compare, swap and pointer move, with a plain-language explanation, the matching line of code, and the Big-O cost.

**Live demo:** https://mariyum008.github.io/dsa-visualizer/

---

## Features

- **453 problems, searchable.** Covers Striver's A2Z DSA sheet in its 18 steps, plus the most-asked interview questions (Blind 75 / NeetCode staples). Filter by topic, difficulty (Easy / Medium / Hard), "Most asked" or "Ready to play".
- **39 built-in animations.** Sorting, searching, two pointers, sliding window, stacks, hashing, linked lists, trees, recursion, dynamic programming and graphs (BFS, DFS, Dijkstra).
- **62 code solutions you can watch run.** Each one has a one-line problem statement and a JavaScript solution that plays step by step.
- **Trace your own code.** Write any JavaScript solution and the page turns every read, write and swap into a step. No AI and no server needed.
- **Data structure guides.** Array, linked list, stack, queue, tree, heap, trie, graph, hash map and set. Each guide has a simple analogy, an operation-speed table, the Python equivalent and practice problems.
- **Two levels of explanation.** Every step has a "simple words" line and a precise "for engineers" line.
- **Your own input.** Type your own numbers, text or grids, or press Shuffle.
- **Works on a phone**, in light and dark mode, and with the keyboard (`Space` plays or pauses, `←` `→` step).

## Topics covered

| Section | Examples |
|---|---|
| Arrays | Two Sum, Kadane's, Best Time to Buy and Sell Stock, Product of Array Except Self, Rotate Array |
| Strings | Valid Anagram, Group Anagrams, Palindrome Check |
| Two Pointers & Sliding Window | 3Sum, Container With Most Water, Longest Substring Without Repeating Characters, Minimum Window Substring |
| Stack & Queue | Valid Parentheses, Min Stack, Daily Temperatures, Sliding Window Maximum, LRU Cache |
| Binary Search | Search in Rotated Sorted Array, Find Minimum in Rotated Sorted Array |
| Linked List | Reverse, Middle, Cycle Detection, Merge Two Sorted Lists, Remove Nth From End |
| Trees & BST | Traversals, Max Depth, Invert, Validate BST, LCA, Serialize |
| Heaps & Tries | Kth Largest, Top K Frequent, Merge K Sorted Lists, Median from Data Stream, Implement Trie |
| Graphs | BFS, DFS, Dijkstra, Number of Islands, Rotting Oranges, Course Schedule, Clone Graph |
| Dynamic Programming | Fibonacci, Climbing Stairs, House Robber, Coin Change, LIS, LCS, Word Break |
| Recursion & Backtracking | Tower of Hanoi, Subsets |

## How to use

1. Open the live link, or download `index.html` and double-click it.
2. Search for a problem in the sidebar, or pick a topic.
3. Problems tagged **Play** open an animation. Problems tagged **Code** open a runnable solution.
4. Press **Play**, or step through with the arrow buttons. Change the input and press **Use these** to try your own.

## Trace your own code

Click **Trace my code**, write a function called `solve`, and press **Run & visualise**.

```js
function solve(a) {
  for (let i = 0; i < a.length - 1; i++)
    for (let j = 0; j < a.length - 1 - i; j++)
      if (a[j] > a[j + 1]) [a[j], a[j + 1]] = [a[j + 1], a[j]];
  return a;
}
```

**Helpers you can call:**

| Helper | What it does |
|---|---|
| `point('i', i)` | Shows a pointer label under spot `i` (`point('cell', r, c)` for grids) |
| `done(i)` | Paints spot `i` green |
| `track('Stack', [])` | Shows a stack, queue or hash map (`{}`) as its own panel |
| `show('sum', sum)` | Shows a variable's value |
| `note('text')` | Adds your own explanation step |

**Input formats:**

| Type this | You get |
|---|---|
| `5, 3, 8, 1` | A list of numbers |
| `hello` | A list of characters |
| `3, 9, 20, null, null, 15, 7` | A tree stored level by level (children of `i` are at `2i+1`, `2i+2`) |
| `1 1 0; 0 1 0; 0 0 1` | A grid (rows separated by `;`) |
| `["eat","tea"]` or `[[1,3],[2,6]]` | A list of words, or a list of pairs |

Your code runs in a sandboxed Web Worker. It stops after 4 seconds or 6,000 actions, so endless loops cannot freeze the page.

## Tech

- A single self-contained `index.html` with plain HTML, CSS and JavaScript, no frameworks and no build step
- SVG for trees, graphs and linked lists
- A JavaScript `Proxy` inside a Web Worker records every array read and write for the code tracer
- Google Fonts: Fredoka, Nunito and JetBrains Mono. The page falls back to system fonts when offline.

## Run locally

```bash
git clone https://github.com/Mariyum008/dsa-visualizer.git
cd dsa-visualizer
# then open index.html in your browser
```

## Notes

- The **Ask Claude** button only works when the page is opened inside Claude (claude.ai). Everything else works anywhere.
- The problem list follows the well-known version of Striver's A2Z DSA sheet. The current version on takeuforward.org may name or group a few problems differently.

## Credits

- Problem list based on [Striver's A2Z DSA Sheet](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2) by Raj Vikramaditya (takeUforward)
- Interview problem set inspired by Blind 75 and NeetCode
