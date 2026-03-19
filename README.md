# Delivery Cannon Project

Source code for DeliveryCannon, created for Ludum Dare 53. A 2D Unity game focused on time management and physics-based delivery mechanics. 

## Mechanics
* **Movement:** Top-down 2D movement.
* **Delivery System:** Aim and shoot packages using a cannon. Firing induces player knockback and a temporary movement penalty.
* **Inventory:** Collect packages via collision (maximum capacity: 9). Select active packages using numerical keys.
* **Request System:** Houses dynamically generate delivery requests with strict time limits. Delivering the correct requested package results in a success state; failing the time limit results in a fail state.
* **Game Loop:** Fixed duration gameplay managed by a centralized timer, handling pause and game-over states.

## Core Scripts
* `GameManager.cs`: Controls `GameState` (Gameplay, Paused, GameOver) and global session timers.
* `PackageCannon.cs`: Handles mouse-tracking rotation, package selection, and instantiation of package projectiles.
* `PlayerMovement.cs`: Manages velocity, input vectors, and applies shooting knockback forces via `Rigidbody2D`.
* `PlayerPickup.cs`: Controls trigger-based package collection and enforces the maximum inventory limit.
* `House.cs`: Manages randomized request generation, success/failure validation upon collision, and independent wait timers.

## Requirements
* Unity (2022+ recommended)
* Universal Render Pipeline (URP)
* 2D Physics

## Component Summary

| Component | Description | File Path |
| :--- | :--- | :--- |
| **Game Manager** | Handles game states and session runtime limits. | [GameManager.cs](Assets/__Scripts/Managers/GameManager.cs) |
| **Cannon** | Controls aiming, firing events, and queue management. | [PackageCannon.cs](Assets/__Scripts/Packages/PackageCannon.cs) |
| **Movement** | Manages speed, input processing, and recoil physics. | [PlayerMovement.cs](Assets/__Scripts/Player/PlayerMovement.cs) |
| **Inventory** | Handles object acquisition up to a limit of 9 items. | [PlayerPickup.cs](Assets/__Scripts/Player/PlayerPickup.cs) |
| **House Logic** | Controls random delivery requests and timeout logic. | [House.cs](Assets/__Scripts/House.cs) |
