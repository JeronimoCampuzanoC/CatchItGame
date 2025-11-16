# CatchItGame 🎮

A rhythm-based catching game built for the Hack computer platform using the Jack programming language. Test your reflexes by catching falling card suit sprites (Hearts ♥, Spades ♠, Diamonds ♦, Clubs ♣) at the perfect moment!

## 🎯 Game Description

CatchItGame is an interactive arcade-style game where players must press the correct arrow key when sprites reach the target zone. The game features:

- **4 Card Suit Sprites**: Heart, Spade, Diamond, and Club
- **Dynamic Difficulty**: Speed increases every 20 points
- **Score System**: Gain points for successful catches, lose points for misses
- **Visual Feedback**: Decorative screen dividers and score display
- **Progressive Challenge**: Sprites drop in randomized patterns

## 🎮 How to Play

### Controls

- **Left Arrow (130)**: Catch the Heart sprite (Column 1)
- **Up Arrow (131)**: Catch the Spade sprite (Column 2)
- **Down Arrow (133)**: Catch the Diamond sprite (Column 3)
- **Right Arrow (132)**: Catch the Club sprite (Column 4)

### Gameplay

1. Watch for sprites falling down their respective columns
2. Press the corresponding arrow key when a sprite enters the target zone (horizontal lines)
3. Successfully caught sprites earn +1 point
4. Missed sprites (reaching the bottom) lose -1 point
5. Game speed increases every 20 points for added challenge

## 🛠️ Technical Requirements

- **Platform**: Hack Computer / nand2tetris
- **Language**: Jack
- **Tools**: Jack Compiler, VM Emulator
- **Screen Resolution**: 512 x 256 pixels

## 📦 Project Structure

```
CatchItGame/
├── Main.jack              # Main game loop and logic
├── HeartSprite.jack       # Heart sprite class
├── SpadeSprite.jack       # Spade sprite class
├── DiamondSprite.jack     # Diamond sprite class
├── ClubSprite.jack        # Club sprite class
├── Points.jack            # Score management and display
├── Dropper.jack           # Sprite spawning controller
├── ScreenInitial.jack     # Screen layout and decorations
└── README.md              # This file
```

## 🚀 How to Compile and Run

### Step 1: Compile the Jack Code

Navigate to your nand2tetris tools directory and run the Jack Compiler:

```bash
cd ~/Downloads/nand2tetris/tools
bash JackCompiler.sh Downloads/CatchItGame/
```

This will compile all `.jack` files into `.vm` files.

### Step 2: Run the Game

Launch the VM Emulator:

```bash
bash VMEmulator.sh
```

Then in the VM Emulator:

1. Load the compiled program directory: `Desktop/university/computer-org/CatchItGame/`
2. Set the animation speed to no animation
3. Click "Run" to start the game

## 🎨 Game Features

### Object-Oriented Design

- Each sprite is an independent object managing its own state
- Modular class structure for easy maintenance and expansion
- Encapsulated game logic in specialized classes

### Visual Elements

- **Score Display**: "Score" text rotated 90° clockwise with live point counter
- **Decorative Dividers**: Diamond pattern vertical separators between columns
- **Target Zone**: Horizontal lines indicating the catch window
- **Sprite Graphics**: Custom-drawn 32x32 pixel card suit shapes

### Dynamic Gameplay

- Randomized sprite drop sequence (12 sprites per cycle)
- 60-frame intervals between drops (~1 second at 16ms/frame)
- Adaptive difficulty with speed progression
- Collision detection with precise timing window

## 🧩 Game Mechanics

### Sprite Dropping Pattern

The game uses a predetermined but varied sequence:

- Interval: Every 60 frames
- Sequence: Spade → Club → Heart → Diamond → Heart → Club → Spade → Diamond → Heart → Spade → Club → Diamond
- Cycle resets after 720 frames

### Scoring System

- **Successful Catch**: +1 point (must be within 8-pixel window)
- **Missed Sprite**: -1 point (sprite reaches bottom)
- **Minimum Score**: 0 (scores cannot go negative)

### Speed Progression

- **Starting Speed**: 2 pixels per frame
- **Increase Rate**: +1 speed every 20 points
- **Effect**: Makes sprites fall faster, reducing reaction time

## 👨‍💻 Development

### Architecture

- **Main Loop**: Handles game state, input, and rendering
- **Sprite Classes**: Independent objects with position, state, and rendering methods
- **Points System**: Manages scoring with automatic display updates
- **Dropper Controller**: Manages sprite activation timing

### Memory Management

- Proper object disposal to prevent memory leaks
- Efficient rendering with erase/draw cycles
- Boundary checking to prevent illegal coordinates

## 📝 Notes

- Game runs at approximately 60 FPS (16ms frame time)
- Target zone provides 8-pixel margin for catching sprites
- Sprites are 32 pixels tall, starting at y=0
- Screen coordinates: (0,0) top-left to (511,255) bottom-right

## 🎓 Educational Context

This project was developed as part of a Computer Organization course, demonstrating:

- Low-level graphics programming
- Object-oriented design in Jack
- Memory management in resource-constrained environments
- Game loop implementation
- User input handling
- Real-time rendering techniques

## 📄 License

This project is educational software developed for the nand2tetris course.

---

**Enjoy the game and challenge your reflexes! 🎮✨**
