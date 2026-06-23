# ⚡ QuickSort Visualizer

> **Watch QuickSort think — step by step.** A fully interactive, zero-dependency browser tool that animates every comparison, swap, and partition of the QuickSort algorithm with live pseudocode highlighting, call-stack inspection, and more.

![Zero Dependencies](https://img.shields.io/badge/Zero%20Dependencies-100%25%20Vanilla-brightgreen?style=flat-square)
![Single File](https://img.shields.io/badge/Single%20File-HTML%20%2B%20CSS%20%2B%20JS-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## 🌐 Live Demo

👉 **[https://github.com/Bsai-24071/Quicksort-visualizer](https://github.com/Bsai-24071/Quicksort-visualizer)**

---

## 🚀 How to Run (3 Seconds Setup)

There is **no installation, no npm, no build step** needed. It's a single HTML file.

### Step 1 — Clone the repository
```bash
git clone https://github.com/Bsai-24071/Quicksort-visualizer.git
```

### Step 2 — Go into the folder
```bash
cd Quicksort-visualizer
```

### Step 3 — Open in your browser

**Windows:**
```bash
start quicksort-visualizer.html
```

**macOS:**
```bash
open quicksort-visualizer.html
```

**Linux:**
```bash
xdg-open quicksort-visualizer.html
```

Or simply **double-click** `quicksort-visualizer.html` in your file explorer.

> ✅ Works in Chrome, Firefox, Edge, and Safari. No internet required after opening.

---

## 🗺️ Full Feature Walkthrough

Here is a complete guide to every button and section of the visualizer so you know exactly what each thing does.

---

### 🔝 Header

At the very top of the page you will see:

```
quick_sort()  Visualizer                              O(n log n) avg
```

- **Left side** — the name of the tool.
- **Right side** — a green badge showing the average time complexity of QuickSort.

---

### 🎛️ Toolbar Row 1 — Pattern Buttons

```
Pattern:  [ Random ]  [ Sorted ]  [ Reversed ]  [ Nearly sorted ]  [ Few unique ]
```

These buttons control **what kind of array is generated** before sorting.

| Button | What it does | Why it's useful |
|---|---|---|
| **Random** *(default, purple)* | Generates numbers at random between 5 and 100 | Good for general use |
| **Sorted** | Generates an already ascending-sorted array | Shows **O(n²) worst case** when combined with Last pivot |
| **Reversed** | Generates a descending-sorted array | Another worst-case trigger |
| **Nearly sorted** | Sorted array with a few random swaps | Realistic real-world data |
| **Few unique** | Only 5 distinct values, lots of duplicates | Tests equal-element handling |

**👆 How to use:**
1. Click any pattern button — it turns **purple/highlighted**.
2. A new array is generated and displayed immediately as bars.
3. The previous sort is cleared automatically.

> 💡 **Try:** Click **Sorted** then set **Pivot → Last** — watch comparisons explode to O(n²)!

---

### 🎛️ Toolbar Row 2 — Pivot, Size, Speed

#### Pivot Strategy

```
Pivot:  [ Last ]  [ First ]  [ Median-3 ]  [ Random ]
```

Controls **which element is chosen as the pivot** during each partition step.

| Button | Strategy | Effect |
|---|---|---|
| **Last** *(default, orange)* | Always picks the last element | Fast for random data, worst for sorted |
| **First** | Always picks the first element | Similar to Last but mirrors worst case |
| **Median-3** | Picks the median of first, middle, last | Best practical performance |
| **Random** | Picks a random element each time | Avoids pathological worst cases |

**👆 How to use:**
1. Click a pivot button — it turns **orange/highlighted**.
2. A new array is generated automatically with the new strategy applied.
3. Watch the **orange bar** (pivot) change position in each partition.

---

#### Size Slider

```
Size:  [━━━●━━━━━━]  20
```

- **Drag left** → fewer bars (minimum **5**)
- **Drag right** → more bars (maximum **80**)
- The number on the right updates live.
- A new array is generated immediately when you let go.

> 💡 Set size to **5–10** when learning — you can clearly follow each step. Set to **60–80** for a beautiful full-screen animation.

---

#### Speed Slider

```
Speed:  [━━━●━━━━━━]  4×
```

- **Drag left** → slower (1× = 200ms per step, good for studying)
- **Drag right** → faster (10× = 5ms per step, fast-forward mode)
- You can **change speed while sorting is running** — takes effect immediately.

---

### 🎛️ Toolbar Row 3 — Custom Array & Action Buttons

#### Custom Array Input

```
[ Custom array: e.g. 38, 27, 43, 3, 9, 82, 10 ]   [ Load ]
```

**👆 How to use:**
1. Click inside the text box.
2. Type your own numbers separated by commas, e.g.: `15, 3, 90, 42, 7, 55`
3. Click **Load** — your custom array appears as bars and is ready to sort.

> ⚠️ Needs at least **2 numbers**. Values above 999 are capped at 999.

---

#### Action Buttons

| Button | Color | What happens when you click it |
|---|---|---|
| **▶ Sort** | Purple | Starts auto-playing the entire sort animation at the selected speed |
| **⏸ Pause** | Appears mid-sort | Pauses the animation at the current step |
| **▶ Resume** | Orange | Continues from exactly where it paused |
| **Step →** | Grey | Advances **exactly one operation** (one compare, one swap, etc.) — great for studying |
| **↺ New** | Grey | Generates a brand-new random array of the current size and resets everything |
| **✕ Reset** | Red outline | Same as New — clears the sort and generates a fresh array |

**👆 Typical learning workflow:**
1. Choose a **Pattern** and **Pivot** strategy.
2. Set **Speed to 1×** (slowest).
3. Click **Step →** repeatedly and read the explanation box after each step.
4. When you understand, click **▶ Sort** to watch it play automatically.

---

### 📊 Progress Bar

```
[━━━━━━━━●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━] 
```

A thin bar below the toolbars shows overall sort progress.

- The **dot (●)** moves right as each step is completed.
- **Click anywhere on the bar** to jump to that point in the animation instantly.
  - The visualiser replays internally up to that point so all colors and states are correct.
- Works like a video scrubber — you can jump forwards or backwards.

> 💡 Click near the **end** of the progress bar to skip to the final sorted state.

---

### 💬 Step Explanation Box

```
┌─────────────────────────────────────────────┐
│ COMPARING                          42 / 186 │
│ Comparing arr[3] = 27 with pivot 43         │
│ → ≤ pivot, will swap                        │
└─────────────────────────────────────────────┘
```

This box updates after **every single operation** and tells you exactly what is happening.

| Part | Meaning |
|---|---|
| **Tag** (top-left, e.g. `COMPARING`) | The type of current operation |
| **Main text** | A plain-English description of what just happened and why |
| **Counter** (top-right, e.g. `42 / 186`) | Current step number out of total steps |

**Operation types you'll see:**

| Tag | Meaning |
|---|---|
| `READY` | Array loaded, waiting to start |
| `RECURSION` | `quickSort()` was called on a subarray |
| `PIVOT SELECTED` | A pivot element was chosen |
| `MOVING PIVOT` | Pivot swapped to end before partitioning (for non-Last strategies) |
| `COMPARING` | Two elements are being compared against the pivot |
| `SWAPPING` | Two elements are being swapped |
| `PIVOT PLACED` | Pivot has found its final sorted position ✓ |
| `BASE CASE` | Single element — already sorted |
| `SUBARRAY DONE` | A subarray is fully sorted |
| `✓ COMPLETE` | Entire array is sorted! |

---

### 📊 Bar Chart (The Main Arena)

The large colored bar chart in the center is the heart of the visualizer.

**Each bar = one element in the array.**
- **Taller bar** = larger value
- **Shorter bar** = smaller value

#### Bar Colors (Legend at bottom of arena)

| Color | Meaning |
|---|---|
| 🔵 Dark blue `#3a4a7a` | Unsorted / not currently active |
| 🟠 Orange | **Pivot** — the element partitions are being built around |
| 🔵 Cyan | **Comparing** — being tested against the pivot right now |
| 🩷 Pink | **Swapping** — two elements swapping positions |
| 🔵 Blue | **Left partition** — elements already confirmed ≤ pivot |
| 🟣 Purple | **Right partition** — elements already confirmed > pivot |
| 🟢 Green | **Sorted** — confirmed in its final position forever |

#### Pivot Arrow

When an element is selected as pivot, a small `▼ pivot` label appears **above** the bar:

```
▼ pivot
  ┃
  █
```

#### Value & Index Labels

- If bars are wide enough, the **numeric value** appears below each bar.
- The **index number** (position in array) appears beneath the value.
- These hide automatically on small bars to avoid clutter.

---

### 📈 Stats Cards (Bottom of Left Column)

Four cards update in real time as the sort runs:

```
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐
│    142   │ │    23    │ │   388    │ │    6     │
│Comparisons│ │  Swaps   │ │  Array   │ │  Max     │
│          │ │          │ │ accesses │ │  depth   │
└──────────┘ └──────────┘ └──────────┘ └──────────┘
```

| Stat | What it counts |
|---|---|
| **Comparisons** | Every time `arr[j] <= pivot` is evaluated |
| **Swaps** | Every time two elements change positions |
| **Array accesses** | Total read + write operations on the array |
| **Max depth** | Deepest recursion level reached (shows at start) |

> 💡 Watch **Comparisons** — with **Sorted + Last pivot** it reaches ~n²/2. With **Median-3** it stays near n·log₂(n).

---

### 📋 Right Panel — 4 Tabs

Click the tabs at the top of the right panel to switch views.

---

#### Tab 1: Code (Pseudocode)

```
function quickSort(arr, lo, hi):       ← click to see this tab
  if lo < hi:
▶   p = partition(arr, lo, hi)         ← highlighted line (purple)
    quickSort(arr, lo, p-1)
    quickSort(arr, p+1, hi)

function partition(arr, lo, hi):
  pivot = arr[hi]  // chosen by strategy
  i = lo - 1
  for j = lo to hi - 1:
    if arr[j] <= pivot:
      i++
      swap(arr[i], arr[j])
  swap(arr[i+1], arr[hi])
  return i + 1
```

- The **currently executing line is highlighted in purple** after every step.
- Syntax is color-coded: keywords in pink, variables in yellow, functions in cyan, numbers in purple.
- Great for following along with a textbook or lecture.

---

#### Tab 2: Stack (Call Stack)

Shows the **live recursion call stack** — every active `quickSort()` call currently open.

```
┌────────────────────────────────┐
│ qs(0, 19)            depth 0  │  ← active frame (purple border)
│ qs(0, 8)             depth 1  │
│ qs(0, 3)             depth 2  │
└────────────────────────────────┘

Recursion depth
[sparkline chart showing depth over time]
```

- The **top frame** (purple border) is the currently active recursive call.
- Frames below it are the parent calls waiting to resume.
- The **sparkline chart** at the bottom shows how recursion depth has changed over time — peaks = deepest recursion.

---

#### Tab 3: Log (Operation Log)

A scrollable chronological log of every operation:

```
quickSort called on subarray [0…19], depth 0
Pivot = 43 at index [19]. Scanning subarray [0…19]
Comparing arr[0] = 15 with pivot 43 → ≤ pivot, will swap
Comparing arr[1] = 72 with pivot 43 → > pivot, skip
Swap arr[1] = 72 ↔ arr[2] = 31
...
```

- Color-coded: **orange** for pivot events, **pink** for swaps, **green** for sorted confirmations.
- Keeps the last **200 entries**.
- Auto-scrolls to the latest entry.
- Useful for reviewing what happened after a fast auto-play.

---

#### Tab 4: Info (Algorithm Reference)

A quick-reference card:

**Time Complexity**
| Case | Complexity |
|---|---|
| Best | O(n log n) |
| Average | O(n log n) |
| Worst | O(n²) — shown in red |

**Space Complexity**
| | |
|---|---|
| Stack (average) | O(log n) |
| Stack (worst) | O(n) |
| In-place? | ✅ Yes |
| Stable? | ❌ No |

Includes a note explaining **exactly how to trigger the worst case** in the visualizer.

---

## 🎮 Example Walkthroughs

### Walkthrough 1 — See O(n²) Worst Case
1. Click **Sorted** (Pattern row)
2. Click **Last** (Pivot row) — it should already be selected
3. Set **Size** to 30
4. Set **Speed** to 8×
5. Click **▶ Sort**
6. Watch **Comparisons** skyrocket — the pivot always ends up at one end!

### Walkthrough 2 — Step Through Manually
1. Click **↺ New** to get a fresh random array
2. Set **Size** to 8 (small, easy to follow)
3. Set **Speed** to 1×
4. Switch right panel to **Code** tab
5. Click **Step →** one at a time
6. Read the explanation box after each click
7. Watch the highlighted line in the Code tab follow along

### Walkthrough 3 — Compare Pivot Strategies
1. Set **Size** to 50, **Pattern** to **Sorted**
2. Click **Last** pivot → click **▶ Sort** → note the Comparisons count
3. Click **↺ New** → click **Median-3** pivot → click **▶ Sort** → compare Comparisons count
4. The difference shows why pivot choice matters!

### Walkthrough 4 — Use a Custom Array
1. Click inside the **custom input box**
2. Type: `64, 34, 25, 12, 22, 11, 90`
3. Click **Load**
4. Click **Step →** slowly and trace through each partition yourself

---

## 📁 Project Structure

```
Quicksort-visualizer/
├── quicksort-visualizer.html   ← entire app (HTML + CSS + JS, single file)
└── README.md                   ← this file
```

The full application is a **single self-contained HTML file** — no frameworks, no build tools, no package.json. Share the `.html` file with anyone and it works instantly.

---

## 🐛 Bugs Fixed

This version addresses three root-cause bugs from earlier builds:

| # | Bug | Root Cause | Fix Applied |
|---|---|---|---|
| 1 | Bars were gigantic / overflowed arena | `container.clientHeight` returned `0` on first render | Replaced with `ResizeObserver` that tracks actual height at all times |
| 2 | Old bars from previous array bled through | DOM was only conditionally cleared when bar count changed | Added explicit `innerHTML = ''` force-clear on every new array |
| 3 | Pattern buttons lost their highlight | Active state used fragile text-content substring matching | Replaced with ID-based lookup using `PATTERN_IDS` and `PIVOT_IDS` arrays |

---

## 🌐 Browser Support

| Browser | Supported |
|---|---|
| Chrome 80+ | ✅ Full support |
| Firefox 75+ | ✅ Full support |
| Edge 80+ | ✅ Full support |
| Safari 14+ | ✅ Full support |
| Mobile browsers | ✅ Responsive layout |

---

## 🎨 Tech Stack

| Technology | Usage |
|---|---|
| **HTML5** | Structure and semantic markup |
| **Vanilla CSS** | Full design system with CSS variables, animations, glassmorphism |
| **Vanilla JavaScript** | Algorithm, step-builder, DOM rendering, ResizeObserver |
| **Google Fonts** | JetBrains Mono + Inter typefaces |
| **Canvas API** | Recursion depth sparkline chart |

---

## 📜 License

MIT — free to use, learn from, modify, and share.

---

*Made with ❤️ — 100% vanilla HTML/CSS/JS, zero dependencies.*
