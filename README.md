# ⚡ QuickSort Visualizer

An interactive, feature-rich browser-based tool that lets you **see QuickSort think** — step by step, with live pseudocode highlighting, call-stack inspection, operation logs, and configurable pivot strategies.

![QuickSort Visualizer Preview](https://img.shields.io/badge/Zero%20Dependencies-100%25%20vanilla-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![HTML](https://img.shields.io/badge/HTML%20%2B%20CSS%20%2B%20JS-single%20file-orange?style=flat-square)

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/quicksort-visualizer.git
cd quicksort-visualizer

# 2. Open directly in your browser — no build step needed!
start quicksort-visualizer.html      # Windows
open  quicksort-visualizer.html      # macOS
xdg-open quicksort-visualizer.html  # Linux
```

> **That's it.** There are **zero dependencies** and **no npm install** required. The entire application is a single self-contained HTML file.

---

## ✨ Features

### 🎯 Core Visualisation
| Feature | Description |
|---|---|
| **Animated bar chart** | Every comparison, swap, and partition is animated in real time |
| **Color-coded states** | Pivot 🟠, Comparing 🔵, Swapping 🩷, Sorted 🟢, Left/Right partitions |
| **Pivot arrow** | A `▼ pivot` label floats above the current pivot bar |
| **Smooth transitions** | CSS cubic-bezier transitions for height and color changes |

### ⚙️ Pivot Strategies
Choose between four pivot-selection strategies to explore their effect on performance:

| Strategy | Description |
|---|---|
| **Last** | Classic Lomuto partition – always picks the rightmost element |
| **First** | Picks the leftmost element (worst case on sorted arrays) |
| **Median-of-3** | Picks the median of first, middle, and last element |
| **Random** | Picks a random element – good average-case guarantee |

> 💡 **Tip:** Set **Sorted array + Last pivot** and watch comparisons spike to O(n²)!

### 📊 Array Patterns
Generate arrays with different characteristics to stress-test the algorithm:

| Pattern | Description |
|---|---|
| **Random** | Uniformly random values |
| **Sorted** | Already sorted (ascending) |
| **Reversed** | Sorted descending (worst case for Last pivot) |
| **Nearly sorted** | Mostly sorted with a few random swaps |
| **Few unique** | Only 5 distinct values — lots of duplicates |

### 🎮 Playback Controls
| Button | Action |
|---|---|
| **▶ Sort** | Auto-play the entire sort at the selected speed |
| **⏸ Pause / ▶ Resume** | Pause mid-sort and resume at any time |
| **Step →** | Advance exactly one operation at a time |
| **↺ New** | Generate a fresh random array of the same size |
| **✕ Reset** | Reset everything and re-generate |

### 📐 Adjustable Parameters
- **Size slider** — 5 to 80 elements
- **Speed slider** — 1× to 10× (controls animation delay from 200 ms down to 5 ms)
- **Custom array** — Type your own comma-separated numbers, e.g. `38, 27, 43, 3, 9, 82, 10`

### 📍 Progress Scrubber
Click anywhere on the progress bar to **jump to any point** in the animation. The visualiser replays internally to ensure the sorted-set state is always consistent.

### 📋 Right Panel Tabs
| Tab | Contents |
|---|---|
| **Code** | Pseudocode with the **currently executing line highlighted** in real time |
| **Stack** | Live call-stack frames + recursion-depth sparkline chart |
| **Log** | Chronological operation log (last 200 entries, color-coded by type) |
| **Info** | Time/space complexity reference table with notes on worst-case triggers |

### 📈 Live Stats
Four stat cards update with every step:
- **Comparisons** — total element comparisons
- **Swaps** — total element swaps
- **Array accesses** — total read/write operations
- **Max depth** — maximum recursion depth reached

---

## 🐛 Bugs Fixed in This Version

This release addresses three root-cause bugs from earlier versions:

| # | Bug | Fix |
|---|---|---|
| 1 | `container.clientHeight` returned `0` or stale values, causing gigantic bars that overflowed the arena | Replaced with a **`ResizeObserver`** that tracks the true rendered height at all times |
| 2 | Old DOM bars bled through when switching to a new array of a different size | Added an explicit **`innerHTML = ''`** force-clear in `initVisualizer()` before rebuilding |
| 3 | Pattern button active state used a fragile text-content substring match that broke when button labels contained spaces or capital letters | Replaced with an **ID-based lookup** using a fixed `PATTERN_IDS` array |

---

## 📁 Project Structure

```
quicksort-visualizer/
└── quicksort-visualizer.html   # Complete self-contained application
└── README.md                   # This file
```

The entire application — HTML structure, CSS design system, and JavaScript logic — lives in a **single file** for maximum portability. Just share the `.html` file and it works anywhere.

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#0d0f14` | Page background |
| `--surface` | `#161923` | Header / right panel |
| `--panel` | `#1e2433` | Cards, arena |
| `--accent` | `#6c63ff` | Primary interactive color |
| `--pivot` | `#f5a623` | Pivot element highlight |
| `--compare` | `#00c9ff` | Elements being compared |
| `--swap` | `#ff5ea0` | Elements being swapped |
| `--sorted` | `#22d98c` | Confirmed sorted elements |

Typography: **JetBrains Mono** (monospace) + **Inter** (sans-serif), loaded from Google Fonts.

---

## 🧠 Algorithm Details

### Partition (Lomuto scheme)
```
function partition(arr, lo, hi):
  pivot = arr[hi]          // chosen by strategy
  i = lo - 1
  for j = lo to hi - 1:
    if arr[j] <= pivot:
      i++
      swap(arr[i], arr[j])
  swap(arr[i+1], arr[hi])
  return i + 1
```

### Complexity
| Case | Time | Space (stack) |
|---|---|---|
| Best | O(n log n) | O(log n) |
| Average | O(n log n) | O(log n) |
| Worst | O(n²) | O(n) |

QuickSort is **in-place** and **not stable**.

---

## 🖥️ Browser Compatibility

Works in all modern browsers — no polyfills needed.

| Browser | Supported |
|---|---|
| Chrome 80+ | ✅ |
| Firefox 75+ | ✅ |
| Edge 80+ | ✅ |
| Safari 14+ | ✅ |

---

## 📜 License

MIT — free to use, modify, and distribute.

---

*Built with ❤️ using 100% vanilla HTML, CSS & JavaScript — no frameworks, no build tools, no dependencies.*
