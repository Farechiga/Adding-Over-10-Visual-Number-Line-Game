# Adding-Over-10-Visual-Number-Line-Game
Simple multi-step process to visualize adding over ten and incorporate subtraction

## Overview

This app randomly generates addition problems where:

- Each addend is between **2 and 9**
- The **sum is between 11 and 19**
- The **larger number is always on the bottom** (magenta bar)

Students work through **three structured steps** to see how a “make 10” strategy works visually:

1. **Find how many to move to make 10**
2. **Find how many are left from the top number**
3. **Add 10 and the leftover to get the final sum**

Everything lives in a **single file**:

- `adding-over-10.html` – contains HTML, CSS, and JavaScript

No build tools, no dependencies.

---

## Visual Design & Conventions

### Number Line

- Vertical number line from **0 to 20** in **1-unit steps**
- Each unit corresponds to a **fixed pixel height** (16px), so:
  - A bar of height 8 units aligns exactly from 0 to 8
  - The **green line at 10** sits precisely on the **10 tick mark**

### Bars & Colors

- **Bottom bar (magenta)** – larger addend  
- **Top bar (blue)** – smaller addend  
- When part of the top number is **“moved down” to fill 10**, that portion is shown in **purple**.
- In Step 3, the right side uses **black bars** to show:
  - A **10-unit bar** (full ten frame)
  - A **smaller black bar** on top for the leftover (the amount above 10)

All bars are locked to the same 0–20 grid as the number line, so heights match the tick marks exactly.

---

## Game Flow

Each problem goes through three screens (steps). The **left side** is always the same original stack; the **right side** shows derived values.

### Step 1 – Make 10

**Prompt:** “How many do we move to make 10?”

- Left:
  - Magenta bar (bottom addend)
  - Blue bar (top addend), divided into:
    - **Purple segment** (amount needed to reach 10)
    - **Blue segment** (leftover)
- Student fills in: `bottom + ___ = 10`

Correct answer → proceeds to Step 2.

---

### Step 2 – Left From the Top Number

**Prompt:** “How many are left from the top number?”

- Left:
  - **Unchanged** original magenta + blue stack from Step 1
- Right:
  - A **purple bar** representing “how many we moved to make 10”  
    - Its **top is flush with the 10 line**
- Student fills in: `top − moved = leftover`

Correct answer → proceeds to Step 3.

---

### Step 3 – Add 10 and the Leftover

**Prompt:** “Add 10 and the leftover.”

- Left:
  - Still the original magenta + blue stack (same as Steps 1 and 2)
- Right:
  - A **10-unit black bar** (ten frame)
  - A **smaller black bar on top** for the leftover
- Student fills in: `10 + leftover = total`

Correct answer:

- Increments the **“Problems completed”** counter
- Triggers a simple **confetti celebration**
