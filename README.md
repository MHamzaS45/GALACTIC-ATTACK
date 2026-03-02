<img width="1599" height="513" alt="image" src="https://github.com/user-attachments/assets/859a66ea-d528-4713-bbce-90b7ac395b62" />


# <a href = https://uwut09.itch.io/galactic-attack>Galactic Attack</a> 

A 2D top-down shooter game built with **Unity**, featuring flexible player movement, projectile combat, enemy AI, and a full UI flow with scoring and multiple levels.

<img width="397" height="223" alt="image" src="https://github.com/user-attachments/assets/2ebf4770-9a76-4b1d-a8fe-70feb1919e37" /> <img width="397" height="223" alt="image" src="https://github.com/user-attachments/assets/efec6a0a-849b-4998-864a-11a24e3bdaa8" />




## Overview

Galactic Attack is a Unity 2D game where the player fights waves of enemies across levels. It supports multiple movement and aiming styles (including an asteroids-like mode), configurable shooting, and win conditions based on defeating a set number of enemies. Score and high score are tracked per session.

You play as an agent of the UGA (United Galactic Alliance) that have been tasked to eliminate the 'aggressor' Chitouin enemy influence that has invaded the planet. Your mission is to destroy all the Chitouin enemy ships that can phase through the environment and destroy you. You will possess only 3 lives for each game so be on guard when facing the hordes of enemies that will be racing to terminate you.

---

## Features

### Player
- **Movement modes**: Horizontal only, vertical only, free roam, or asteroids-style (physics-based with rotation)
- **Aiming**: Aim toward mouse, or aim in movement direction
- **Shooting**: Configurable fire rate, projectile spread, and optional fire effects

### Combat
- **Projectiles**: Customizable prefabs with optional auto-destroy (e.g. by time or distance)
- **Enemies**: Multiple behaviors—follow player, scroll in a direction, or static
- **Enemy shooting**: Optional; enemies can use the same shooting system with multiple guns
- **Health & damage**: Reusable `Health` and `Damage` components for player and enemies

### Game flow
- **Levels**: Main menu plus Level 1, 2, and 3
- **Scoring**: In-game score and persistent high score
- **Win condition**: Optional; win by defeating a configurable number of enemies
- **UI**: Main menu, in-game HUD (score, high score), level load buttons, quit, custom cursor

### Technical
- **Unity Input System**: Uses the new input system for movement and shooting
- **Camera**: Dedicated camera controller for 2D follow/behavior
- **GameManager**: Singleton managing score, high score, player reference, and UI

---

## Controls

Input is managed via the **Unity Input System**. Typical bindings (can be changed in project settings):

| Action   | Default        |
|----------|----------------|
| Move     | WASD / Arrow keys |
| Aim      | Mouse position |
| Fire     | Left click / Fire1 |
| Menu     | UI buttons (click) |

---

## Requirements

- **Unity**: 2020.2.7f1 (or compatible 2020.2.x LTS)
- **Input System**: Unity Input System package (included in project)
- **Platform**: Built for desktop (e.g. Windows/Mac); WebGL and other platforms are supported by Unity

---

## Project structure

```
Assets/
├── Art/                 # Sprites, animations, and visual assets
│   └── Animations/
├── Scenes/              # Game scenes
│   ├── MainMenu.unity
│   ├── Level1.unity
│   ├── Level2.unity
│   └── Level3.unity
├── Scripts/
│   ├── Camera/          # CameraController
│   ├── Enemies/         # Enemy, EnemySpawner
│   ├── Health&Damage/   # Health, Damage
│   ├── Player/          # Controller (movement & aim)
│   ├── ShootingProjectiles/  # ShootingController, Projectile
│   ├── UI/              # UIManager, ScoreDisplay, HighScoreDisplay, etc.
│   └── Utility/         # GameManager, InputManager, etc.
├── Prefabs/             # Reusable game objects (if present)
└── ...
ProjectSettings/         # Unity project configuration
```

---

## Getting started

1. **Clone or download** the repository.
2. **Open in Unity**: Open the project folder in Unity Hub (or Unity 2020.2.7f1).
3. **Open a scene**: In *Assets/Scenes*, open `MainMenu.unity` or any level.
4. **Play**: Press Play in the Editor to run the game.

### Building

- **File → Build Settings**: Add the scenes you want (e.g. MainMenu, Level1, Level2, Level3) and choose your target platform (e.g. Windows, Mac, WebGL).
- **Build** or **Build and Run** to create a standalone executable or WebGL build.

---

## Configuration

Key settings are exposed in the Inspector:

- **Player (Controller)**: `moveSpeed`, `aimMode`, `movementMode`, `rotationSpeed` (asteroids mode)
- **ShootingController**: `fireRate`, `projectileSpread`, `projectilePrefab`, `fireEffect`
- **Enemy**: `moveSpeed`, `scoreValue`, `movementMode`, `shootMode`, `followTarget`, `followRange`
- **GameManager**: `enemiesToDefeat`, `gameIsWinnable`, `highScore` (runtime)

Adjust these per scene or prefab to tune difficulty and feel.

---

### You can play it right <a href = https://uwut09.itch.io/galactic-attack> here! </a>

## Acknowledgments

- Built with [Unity](https://unity.com/)
- Uses Unity 2D Input System for input handling
