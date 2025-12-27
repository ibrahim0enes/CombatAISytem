
# Responsive Combat AI (Event Graph Architecture)

This repository demonstrates a **Responsive Combat AI** built entirely within the **Event Graph** of Unreal Engine 5, bypassing the traditional Behavior Tree system. This architectural choice allows for millisecond-level responsiveness, making the AI feel "alive" and highly reactive to player movements and attacks.

## 🎯 Project Overview

In fast-paced combat design, the delay between a player's action and the AI's reaction can break the immersion. By using an **Event-Driven approach** directly in Blueprints, this system triggers logic instantly based on state changes rather than waiting for the next "Tick" or "Task" evaluation of a behavior tree.

## 🛠 Core Systems

### 1. Movement & Spatial Awareness

The AI maintains a tactical presence through specialized movement functions:

* **MoveBOTTowardsPlayer:** Calculates dynamic intercept vectors. Instead of simple following, it predicts player positioning to create a sense of pressure.
* **Smooth LookAtRotation:** Uses `RInterp To` logic to ensure the AI always faces the threat, facilitating realistic strafing and preventing the AI from exposing its back.
* **Tactical Strafing:** A blend of movement vectors and animations that allow the AI to circle the player, simulating a "duel" atmosphere.

### 2. Combat Intelligence

The combat flow is managed through distance thresholds and animation notifies:

* **PunchFunction:** A modular attack system that selects between different animations (Jab, Hook, Uppercut) based on randomization and range.
* **CalculateBackFrontDistance:** A spatial utility that determines if the AI should be aggressive (closing the gap), defensive (retreating), or maintaining its ground.
* **Event-Based Damage:** Health updates trigger immediate "Hit React" animations, ensuring the player feels the impact of their attacks.

### 3. Feedback & UI (World Space)

* **Dynamic Health Bars:** A 3D World Space Widget that syncs in real-time with the AI's internal variables.
* **Aim Decals:** Ground-projected indicators that help players visualize the AI's focus point and anticipate incoming attacks.
* **Ragdoll Physics:** Upon the `Death Event`, the AI seamlessly transitions from animation to physical simulation.

## 🚀 Technical Advantages

| Feature | Behavior Tree | Event Graph AI (This Project) |
| --- | --- | --- |
| **Reaction Time** | Dependent on Tree Tick Rate | Instant (Event-Based) |
| **Control Flow** | Hierarchical / Complex | Direct / Linear |
| **Debugging** | Visual Tree Debugger | Real-time Blueprint Flow |
| **Use Case** | Complex RPG NPCs | Fast-paced Action/Fighting Games |

## ⚙️ Optimization Note

To ensure high performance, this project avoids using **Event Tick** for heavy calculations. Instead, it utilizes:

* **Timer Handles:** Distance and logic checks run at optimized intervals (e.g., 0.1s).
* **Event Dispatchers:** UI and state updates are only called when a change actually occurs.

## 📦 Installation & Setup

1. Clone the repository into your UE5 project's `Content` folder.
2. Ensure the **Navigation Mesh Bounds Volume** is set up in your level.
3. Open `BP_CombatAI` and adjust the variables in the `AI_Config` category to tweak aggression and speed.


* **Blueprint mantığını anlatan teknik bir makale (Wiki) mi hazırlayalım?**
* **Sisteme "Combo" veya "Parry" (Saldırı Karşılama) mekaniği eklemek için mantık mı kurgulayalım?**
* **Repo için bir "Contribution" (Katkı) kılavuzu mu yazalım?**
