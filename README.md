# Responsive Combat AI (Non-Behavior Tree Architecture)

This project showcases a **High-Response Combat AI** developed in Unreal Engine 5 using a pure **Event Graph** approach. By completely bypassing traditional Behavior Trees (BT), this architecture achieves instantaneous reaction times and fluid tactical movement, ideal for fast-paced action games.

## 🚀 Why No Behavior Tree?

While Behavior Trees are standard, they often introduce "tick-latency" and complexity for fast-paced melee combat. This system uses an **Event-Driven Architecture** to gain:

* **Zero-Latency Reactions:** Logic triggers immediately upon event calls (OnHit, OnRangeChange) without waiting for a BT node tick.
* **Direct Control:** All combat logic—from movement to attack patterns—is handled in a single, traceable execution flow.
* **Frame-Perfect Precision:** Animations and state changes sync perfectly with player inputs.

---

## 🧠 Core Systems

### 1. Advanced Movement & Orientation

* **MoveBOTTowardsPlayer:** Instead of generic pathfinding, this calculates dynamic intercept vectors for aggressive flanking.
* **Smooth LookAtRotation:** Implements real-time interpolation to ensure the AI always maintains face-to-face contact with the threat.
* **Tactical Strafing:** Procedural circling logic that keeps the AI mobile, preventing static "standing and hitting" scenarios.

### 2. Event-Driven Combat Logic

* **PunchFunction:** A modular attack system that selects randomized strikes (Jab, Hook, Uppercut) based on proximity and cooldowns.
* **CalculateBackFrontDistance:** Real-time spatial analysis that dictates whether the AI should push (Aggressive), retreat (Defensive), or hold position.
* **Immediate Feedback:** Hit-react and death sequences are triggered via direct events for maximum impact feel.

### 3. Feedback & World-Space UI

* **Dynamic Health Widget:** A world-space UI component that updates instantly when damage events are received.
* **Aim & Focus Decals:** Visual ground indicators that help players anticipate AI intentions.

---

## 🛠 Technical Implementation

* **Logic Flow:** Managed through custom functions and macros within the Event Graph.
* **Optimization:** Uses **Timer Handles** instead of `Event Tick` for heavy distance calculations (running at 0.1s intervals) to ensure 60+ FPS performance.
* **State Management:** Uses Enums and Boolean gates to manage combat states (Attacking, Recovering, Chasing).

---

## 📦 Setup

1. Copy the project files to your `Content` folder.
2. Ensure a **NavMeshBoundsVolume** is present in your level.
3. Open `BP_CombatAI` to tweak variables like `AggressionLevel` or `AttackRange`.
