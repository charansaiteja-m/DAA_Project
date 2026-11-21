# Zero-Waste Checkout · Algorithm Explorer

An interactive, single-file web application that explores the **Gift Card Zero-Waste Checkout** problem (0/1 Subset-Sum Optimization) across four foundational algorithmic paradigms—comparing their logic, asymptotic complexities, live execution metrics, and runnable Python 3 implementations.

- **Live Demo:** [Add Your Deployed URL Here]
- **Repository:** [Add Your GitHub Repository URL Here]
- **Author:** M Charan Sai Teja

---

## 1. Problem Overview

### What the Problem Is
Given a prepaid gift card with a fixed balance $B$ and a wishlist of $n$ items with prices $p_1, p_2, \dots, p_n$ (where each item can be purchased at most once), select a subset of items whose combined price is **maximized without exceeding $B$**:

$$\max \sum_{i \in S} p_i \quad \text{subject to} \quad \sum_{i \in S} p_i \le B$$

### Why It Matters in Real Life
Millions of prepaid gift cards and corporate meal or wellness vouchers expire partially unspent every year. Because small leftover balances cannot purchase standalone items and split payments are often restricted by merchants, optimizing cart selection recovers otherwise wasted balance.

### What This Program Computes
For any entered or generated balance $B$ and item list, the application evaluates all four algorithms simultaneously and computes:
1. **Selected Cart Items** and **Balance Utilization Meter** (`%` of card used).
2. **Total Amount Spent** vs. **Remaining Unused Waste**.
3. **Exact Operation Count** and **Execution Time (`ms`)**.
4. **Dynamic Python 3 Source Code** pre-populated with your exact test case inputs and ready to copy with one click.

---

## 2. Algorithmic Approaches Compared

| Algorithm | Strategy | Time Complexity | Space Complexity | Guarantees Optimal? |
| :--- | :--- | :---: | :---: | :---: |
| **Brute Force** | Recursively branches into "buy" or "skip" decisions across all $2^n$ subsets without pruning. | $O(2^n)$ | $O(n)$ | Yes |
| **Greedy** | Sorts items descending by price and selects each item that fits in a single pass. | $O(n \log n)$ | $O(n)$ | **No** (Fast heuristic) |
| **Backtracking** | Sorts descending and prunes branches exceeding $B$ or unable to beat the best total via suffix sums; halts early on exact $B$. | $O(2^n)$ *(worst-case)* | $O(n)$ | Yes |
| **Dynamic Programming** | Populates a 1D reachable-sum parent array `parent[0..B]` and reconstructs the optimal subset backward. | $O(n \cdot B)$ | $O(B)$ | Yes |

---

## 3. Interactive Features

* **Randomized Greedy Trap Generator (`Load Sample Data (Greedy Trap)`):** Dynamically generates a fresh balance $B$ and 5-item set on every click where Greedy grabs a large "bait" item early and leaves unspent waste, while Brute Force, Backtracking, and Dynamic Programming achieve **zero waste**.
* **Randomized General Test Generator (`Generate Random Test Case`):** Generates a new random gift card balance and 4–10 uniquely priced wishlist items on every click and executes all four algorithms immediately.
* **Approach Filter Bar:** Compare all 4 algorithms side-by-side in a 2-column grid or isolate any single paradigm in full-width view.
* **Built-In Documentation Modal (`README`):** Accessible directly from the page footer via a native `<dialog>` overlay.
* **Obsidian & Gold Dark Glassmorphism UI:** Crafted with translucent dark panels (`backdrop-filter: blur(16px)`), animated ambient lighting, cubic-eased number counters, and full `prefers-reduced-motion` accessibility support.

---

## 4. Input Constraints & Validation

* **Gift Card Balance ($B$):** Positive whole number up to `5,000,000`.
* **Wishlist Items:** Between `2` and `22` items (preventing $O(2^n)$ Brute Force browser freezes), formatted either as plain numbers (`600, 500, 450`) or `Name: Price` pairs (`Mouse: 600, Hub: 500, Stand: 450`).

---

## 5. How to Run Locally or Deploy

### Run Locally
1. Clone or download this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   ```
2. Open `index.html` (or `Zero-Waste Checkout · Algorithm Explorer.html`) directly in any modern web browser—no build tools, package managers, or backend servers required.

### Deploy on GitHub Pages
1. Push your HTML file (renamed to `index.html`) and `README.md` to a public GitHub repository.
2. Go to **Settings → Pages** in your repository.
3. Under **Build and deployment**, select **Deploy from a branch**, pick `main` and `/ (root)`, and click **Save**.
4. Your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`.

---

*Made and maintained by **M Charan Sai Teja**.*