# Chess Tutor Game

A command-line chess tutor application that helps players solve chess puzzles and learn best moves analysis.

## Features

- 🎯 **Puzzle Solver**: Load and solve chess puzzles
- 📊 **Move Analysis**: Get feedback on your moves and see the best alternatives
- ♟️ **Interactive Board**: Visual representation of chess positions
- 💡 **Best Move Suggestions**: AI-powered analysis using Stockfish engine

## Installation

1. Install Python 3.8 or higher
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download Stockfish chess engine (required for analysis):
   - **Windows**: Download from https://stockfishchess.org/download/
   - **Mac/Linux**: Install via package manager or download from the website
   - Extract and note the path to the `stockfish` executable

## Running the Game

```bash
python main.py
```

On first run, you'll be prompted to provide the path to your Stockfish executable.

## Project Structure

```
chess-tutor/
├── main.py              # Entry point, game loop
├── board.py             # Chess board management and display
├── puzzle_solver.py     # Puzzle loading and logic
├── move_analyzer.py     # Move analysis and evaluation
├── ui.py                # CLI user interface
├── puzzles/
│   └── sample_puzzles.py # Sample puzzle data
└── requirements.txt     # Python dependencies
```

## How to Play

1. Start the game and select a puzzle
2. The board will display the current position
3. Enter your move in UCI format (e.g., `e2e4`)
4. Get feedback on your move
5. See what the best move(s) were
6. Continue to the next puzzle

## Format for Moves

Chess moves are entered using **UCI notation**:
- Format: `<from_square><to_square>[promotion]`
- Example: `e2e4` (move pawn from e2 to e4)
- Promotions: `e7e8q` (promote to queen)

## Extending the Project

### Adding More Puzzles
Edit `puzzles/sample_puzzles.py` and add FEN positions:
```python
PUZZLES = [
    {
        "id": 1,
        "name": "Scholar's Mate",
        "fen": "rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR w KQkq - 0 1",
        "best_moves": ["e2e4"],
        "difficulty": "Easy"
    },
    # Add more puzzles...
]
```

### Customizing Engine Strength
Modify the engine depth/time in `move_analyzer.py`:
```python
self.engine.set_skill_level(20)  # Set difficulty (0-20)
```

## Team Collaboration

This codebase is organized for easy collaboration:
- Each module handles a specific concern (board, analysis, UI)
- Clear function documentation for easy handoff
- Sample puzzles in separate file for easy content addition

## Dependencies

- **python-chess**: Chess logic and validation
- **stockfish**: Chess engine for best-move analysis

## License

Class project - Feel free to modify and extend!
