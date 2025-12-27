# ⚔️ Advanced Combat AI System - Unreal Engine 5

This project is a high-performance, scalable, and tactile Enemy AI Framework built in **Unreal Engine 5**. It moves beyond simple "follow and attack" logic, utilizing professional tools like **Behavior Trees**, **Environment Query System (EQS)**, and **AI Perception** to create a challenging yet fair combat experience.

## 🚀 Key Features

### 🧠 Strategic Decision Making
The AI's "brain" is built on a modular **Behavior Tree** architecture, allowing for seamless transitions between states based on real-time data stored in the **Blackboard**.
* **Modular States:** Idle, Patrol, Investigate, and Combat.
* **Asynchronous Logic:** Optimized to run complex decision-making processes without impacting frame rates.

### ⚔️ Tactical Combat & Pattern Analysis
Combat is not randomized; it is based on **Pattern-based logic** to simulate a skilled opponent.
* **Pattern-Based Attacks:** The AI analyzes player distance and health to execute specific combos and attack varieties.
* **Adaptive Challenge:** Iterative balancing between "Challenge" and "Fairness" to ensure the AI punishes mistakes but remains fun to play against.

### 👁️ Vision-Based Detection (Perception)
A realistic detection system using the **AI Perception Component**.
* **Configurable FOV:** Fully adjustable field-of-view and detection range.
* **Line-of-Sight (LOS) Validation:** Uses raycasting/traces to ensure the AI only reacts when the player is physically visible behind obstacles.

### 👂 Audio Perception System
The AI reacts to world acoustics, adding a layer of stealth gameplay.
* **Distance-Based Sound Detection:** AI detects footsteps, jumps, or combat noises.
* **Suspicion Thresholds:** Different noise levels trigger different reactions, from a simple "look at" to a full investigation.

### 🔍 Intelligent Investigation Mode
When the player is lost, the AI doesn't just stop; it hunts.
* **Last Known Position (LKP):** The AI remembers where it last saw the player.
* **EQS Integration:** The AI queries the environment to scan potential hiding spots, corners, and cover points strategically.

## 🛠️ Technical Implementation

* **Engine:** Unreal Engine 5
* **Logic:** Behavior Trees, Blackboard, EQS (Environment Query System).
* **Senses:** AI Perception (Sight & Hearing).
* **Navigation:** NavMesh Bounds with Dynamic Modifiers.

## 📝 Usage
1. Clone the repository.
2. Open in Unreal Engine 5.
3. Check the `AI` folder for Behavior Tree and Blackboard assets.
4. Place the `BP_Enemy` actor in your scene with a `NavMeshBoundsVolume`.

---
*Developed as a technical showcase of advanced AI systems in Unreal Engine 5.*
