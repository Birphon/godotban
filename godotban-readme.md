# GodotBan

A modern take on the classic Sokoban puzzle game built with Godot 4, featuring procedural level generation, smooth animations, and progressive difficulty scaling.

## 🚀 Play Online

[Play GodotBan Now](your-deployment-url-here) | [Download for Desktop](releases-link)

## 🎮 Game Features

- **Infinite Levels**: Procedurally generated puzzles that never repeat
- **Smart Difficulty**: Adaptive complexity based on player performance
- **Smooth Animations**: Polished movement and particle effects
- **Multiple Themes**: Warehouse, Space Station, Garden, and Cyber themes
- **Undo System**: Step-by-step move reversal
- **Statistics Tracking**: Personal best times and move counts
- **Responsive Controls**: Keyboard, mouse, and gamepad support

## 🎯 Game Mechanics

### Core Gameplay
- Push boxes onto target spots to complete levels
- Cannot pull boxes, only push them
- Avoid getting boxes stuck in corners or against walls
- Complete all target spots to advance to the next level

### Advanced Features
- **Combo System**: Bonus points for efficient solutions
- **Hint System**: Subtle visual cues when stuck
- **Time Attack Mode**: Race against the clock
- **Zen Mode**: Relaxed gameplay without time pressure

## 🛠️ Tech Stack

- **Engine**: Godot 4.2
- **Languages**: GDScript, C# (performance-critical sections)
- **Audio**: Custom sound effects and ambient music
- **Art**: Hand-crafted pixel art sprites
- **Level Generation**: Custom algorithm using constraint satisfaction

## 📋 Prerequisites

- Godot 4.2+ (for development)
- Git LFS (for asset management)

## 🔧 Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/godotban.git
   cd godotban
   ```

2. **Install Git LFS** (for large assets)
   ```bash
   git lfs install
   git lfs pull
   ```

3. **Open in Godot Editor**
   - Launch Godot 4.2
   - Click "Import" and select the `project.godot` file
   - Wait for initial import to complete

4. **Run the game**
   - Press F5 or click the play button
   - Select the main scene when prompted

## 🎨 Art & Assets

### Sprite Specifications
- **Tile Size**: 64x64 pixels
- **Color Palette**: Limited 16-color palette for consistency
- **Animation**: 8-frame movement animations
- **Themes**: 4 complete visual themes with unique tilesets

### Audio Design
- **Music**: Ambient loops for each theme (60-120 BPM)
- **SFX**: Box sliding, success chimes, UI interactions
- **Dynamic Audio**: Volume mixing based on game state

## 🧩 Level Generation Algorithm

```gdscript
# Simplified level generation process
func generate_level(difficulty: int) -> Level:
    var size = calculate_level_size(difficulty)
    var layout = create_base_layout(size)
    var boxes = place_boxes_optimally(layout, difficulty)
    var targets = determine_target_positions(boxes)
    var player_pos = find_optimal_start_position(layout)
    
    return validate_solvability(layout, boxes, targets, player_pos)
```

### Generation Parameters
- **Size Scaling**: 8x8 (Easy) to 20x15 (Expert)
- **Box Count**: 3-15 boxes based on difficulty
- **Complexity Metrics**: Path length, push sequences, dead-end avoidance
- **Validation**: Ensures every generated level is solvable

## 📊 Game Statistics

The game tracks detailed player metrics:
- Levels completed
- Total moves made
- Average solution efficiency
- Time spent playing
- Personal best records
- Preferred difficulty settings

## 🎮 Controls

### Keyboard
- **Arrow Keys/WASD**: Move player
- **Z/Space**: Undo last move
- **R**: Restart current level
- **Esc**: Pause menu
- **H**: Toggle hints

### Gamepad
- **D-Pad/Left Stick**: Movement
- **A Button**: Confirm/Select
- **B Button**: Undo
- **Start**: Pause menu

## 📁 Project Structure

```
godotban/
├── scenes/
│   ├── Game.tscn              # Main game scene
│   ├── LevelGenerator.tscn    # Level generation system
│   ├── UI/                    # User interface scenes
│   └── Effects/               # Particle and animation effects
├── scripts/
│   ├── GameManager.gd         # Core game logic
│   ├── LevelGenerator.gd      # Procedural generation
│   ├── Player.gd              # Player controller
│   ├── Box.gd                 # Box physics and behavior
│   └── SoundManager.gd        # Audio management
├── assets/
│   ├── sprites/               # Game artwork
│   ├── audio/                 # Music and sound effects
│   └── fonts/                 # UI typography
├── data/
│   ├── levels/                # Handcrafted tutorial levels
│   └── themes/                # Visual theme definitions
└── exports/                   # Build outputs
```

## 🏗️ Build Process

### Desktop Builds
```bash
# Windows
godot --headless --export "Windows Desktop" builds/GodotBan_Windows.exe

# macOS
godot --headless --export "macOS" builds/GodotBan_macOS.dmg

# Linux
godot --headless --export "Linux/X11" builds/GodotBan_Linux.x86_64
```

### Web Build
```bash
# HTML5 export
godot --headless --export "HTML5" builds/web/index.html
```

## 🧪 Testing

### Automated Tests
```bash
# Run unit tests (using Gut framework)
godot --headless -s addons/gut/gut_cmdln.gd -gdir=test/unit -gexit
```

### Manual Testing Checklist
- [ ] Level generation produces solvable puzzles
- [ ] Undo system works correctly
- [ ] All visual themes load properly
- [ ] Audio plays without distortion
- [ ] Controls respond accurately
- [ ] Game saves/loads player progress

## 🚀 Deployment

### Web Deployment (itch.io)
1. Export to HTML5
2. Upload to itch.io
3. Configure page settings
4. Enable full-screen mode

### Steam Deployment
1. Set up Steamworks SDK
2. Create app depot
3. Upload builds for Windows/Mac/Linux
4. Configure store page

## ⚡ Performance Optimizations

- **Object Pooling**: Reuse box and particle objects
- **Culling**: Hide off-screen elements
- **Texture Streaming**: Load theme assets on-demand
- **Audio Compression**: Optimized file formats
- **Level Caching**: Store generated levels temporarily

## 🎯 Future Enhancements

- [ ] Multiplayer cooperative mode
- [ ] Level editor for custom puzzles
- [ ] Workshop integration for sharing levels
- [ ] Mobile touch controls
- [ ] Achievement system
- [ ] Leaderboards and competitions
- [ ] VR mode experiment

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/new-theme`)
3. Test thoroughly on multiple platforms
4. Commit with clear messages (`git commit -m 'Add cyberpunk theme'`)
5. Push to branch (`git push origin feature/new-theme`)
6. Submit Pull Request with screenshots/gameplay video

## 🎨 Asset Guidelines

When contributing art assets:
- Follow the established pixel art style
- Use the defined color palettes
- Maintain consistent tile sizing (64x64)
- Include both idle and animation frames
- Test across all themes for consistency

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Game assets are licensed under Creative Commons Attribution 4.0.

## 🙏 Credits

- **Game Design**: Inspired by the original Sokoban by Hiroyuki Imabayashi
- **Music**: Original compositions by [Composer Name]
- **Pixel Art**: Custom artwork created for this project
- **Special Thanks**: Godot community for excellent documentation

## 👨‍💻 Developer

**Your Name**
- Portfolio: [your-gamedev-portfolio.com](https://your-gamedev-portfolio.com)
- GitHub: [@yourusername](https://github.com/yourusername)
- Twitter: [@yourgamedev](https://twitter.com/yourgamedev)
- itch.io: [yourusername.itch.io](https://yourusername.itch.io)

---

🎮 *Puzzle your way through infinite challenges!*