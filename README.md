# wheelo ★ — Interactive Spin-the-Wheel Application

## Project Overview
**wheelo** is a high-fidelity, retro-themed web application designed for randomized selection. It leverages a custom-built **Canvas-based rendering engine** to provide a seamless, interactive user experience. The project adheres to modern web standards, utilizing a responsive "Mobile-First" design philosophy with a "Cream-and-Brown" pixel-art aesthetic.

---

## 🚀 Core Functionalities

* **Dynamic Sector Allocation**: The system calculates and renders wheel segments in real-time based on the `entries` array length, ensuring equal probability distribution for each candidate.
* **Physics-Based Easing**: Implements a **Cubic Ease-Out function** within a `requestAnimationFrame` loop to simulate realistic angular momentum and friction-induced deceleration.
* **Real-Time DOM Synchronization**: Features bi-directional binding where input changes in the sidebar are instantly reflected in the Canvas label rendering.
* **Stateful UI Feedback**:
    * **Bobbing Pointer**: A CSS-animated indicator to enhance visual focus.
    * **Confetti Particle System**: A lightweight JavaScript trigger that generates randomized DOM elements upon landing.
    * **Modal Interlocks**: Confirmation dialogs implemented to prevent accidental state resets.

---

## 🛠️ Technical Stack (University Standards)

| Module | Technology | Implementation Detail |
| :--- | :--- | :--- |
| **Frontend Layout** | HTML5 / CSS3 | Utilizes Flexbox and CSS Variables for modular styling. |
| **Graphics API** | HTML5 Canvas | Handles coordinate transformations (`rotate`, `translate`) for wheel segments. |
| **Typography** | Google Fonts API | Integrated 'Press Start 2P' for a 8-bit retro aesthetic. |
| **Logic Layer** | Vanilla JavaScript | ES6+ syntax for array manipulation and animation timing. |
| **Asset Management** | Embedded Data | Zero external dependencies for maximum portability and fast load times. |

---

## 📂 System Architecture

### 1. The Rendering Pipeline (`drawWheel`)
The wheel is drawn by iterating through the `entries` object. Each slice is assigned a color from a predefined **Palette Constant** based on its index (`seg.idx % PALETTE.length`). Labels are dynamically truncated using `measureText` to ensure they fit within the radius of the wheel.

### 2. The Spin Algorithm (`spinWheel`)
The winning index is pre-determined using `Math.random()`. The system then calculates a `targetRot` that includes several full rotations (8-14 spins) plus a **jitter factor** to ensure visual variety even when landing on the same segment.

---

## 📝 Usage Instructions

1.  **Initialization**: Launch `index.html` in a standard web browser.
2.  **CRUD Operations**: Use the **+ ADD ENTRY** button to append new objects to the state. Click the **X** button to remove specific nodes.
3.  **Execution**: Trigger the `spinWheel()` function via the **SPIN!** button. The button will be disabled during the animation lifecycle to prevent race conditions.
4.  **Reset**: Use the **RESET ALL** function to return the application to its default boilerplate state.

---

*This project was developed as a part of a creative frontend engineering exploration, focusing on the intersection of UI/UX design and mathematical animations.*
