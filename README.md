# 🐍 Snake Game

A fully playable recreation of the classic Snake game built in Python using the `turtle` graphics library and Object-Oriented Programming. Guide the snake to eat food, grow longer, and avoid hitting the walls or yourself!

---

## 📋 Features

- Smooth real-time movement with keyboard controls
- Snake grows longer with every piece of food eaten
- Live score display updated in real time
- Wall and self-collision detection
- Game resets automatically on collision

---

## 🏗️ Project Structure

```
snake-game/
├── main.py          # Entry point — sets up the screen and runs the game loop
├── snake.py         # Snake class — handles movement, growth, and direction
├── food.py          # Food class — spawns food at random positions
└── scoreboard.py    # ScoreBoard class — displays and updates the score
```

---

## 🧱 OOP Design

| Class | Inherits From | Responsibility |
|---|---|---|
| `Snake` | — | Creates and manages all snake segments, handles movement and direction logic |
| `Food` | `turtle.Turtle` | Spawns as a small red circle at a random position; refreshes on collision |
| `ScoreBoard` | `turtle.Turtle` | Renders the score on screen and updates it as the snake eats food |

`Food` and `ScoreBoard` both inherit directly from `turtle.Turtle`, demonstrating **inheritance** to extend built-in library classes with custom behaviour. `Snake` composes multiple `Turtle` instances to represent its body segments, demonstrating **composition**.

---

## 🚀 Getting Started

**Requirements:** Python 3.x — `turtle` is included in the Python standard library, no installs needed!

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/snake-game.git
   cd snake-game
   ```

2. Run the game:
   ```bash
   python main.py
   ```

---

## 🕹️ Controls

| Key | Action |
|---|---|
| `↑` Arrow | Move Up |
| `↓` Arrow | Move Down |
| `←` Arrow | Move Left |
| `→` Arrow | Move Right |

> The snake cannot reverse directly — pressing the opposite direction is ignored to prevent instant self-collision.

---

## ⚙️ Game Logic

- **Movement** — each segment follows the one ahead of it; only the head moves forward each tick
- **Food collision** — detected when the head gets within 15 pixels of the food; food refreshes and a new segment is added
- **Wall collision** — triggers game over when the head exceeds 295px from centre on either axis
- **Self collision** — triggers game over when the head occupies the same position as any body segment
- **Game loop** — runs at 10 frames per second via `time.sleep(0.1)` and `screen.tracer(0)`

---

## 🧠 Concepts Practiced

- Object-Oriented Programming — classes, inheritance, composition
- Inheriting from a third-party class (`turtle.Turtle`)
- Real-time game loop with `turtle` screen updates
- Collision detection using coordinate distance and position comparison
- Keyboard event binding with `screen.onkey()`
- Global state management with `global` keyword

