# AIPathFinder - Dynamic Pathfinding Agent

A comprehensive Python application that visualizes **uninformed** (BFS, DFS, UCS, DLS, IDDFS, Bidirectional) and **informed** (GBFS, A*) search algorithms. Features dynamic grid sizing, random map generation, interactive map editor, dynamic obstacles with re-planning, and real-time metrics (nodes visited, path cost, execution time).

---

## Features

- **Six Search Algorithms**: Implementations of BFS, DFS, UCS, DLS, IDDFS, and Bidirectional Search
- **Real-Time Visualization**: Step-by-step animation showing frontier nodes, explored nodes, and final path
- **Interactive GUI**: Beautiful Matplotlib-based interface with color-coded grid cells
- **Path Visualization**: Green path connects Start to Target with numbered visit order

---

## Requirements

- **Python 3.8+**
- **Dependencies**:
  - `matplotlib` - For GUI visualization
  - `numpy` - For grid operations

---

## 🚀 Installation

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd AI-PathFinder
   ```

2. **Install dependencies**:
   ```bash
   pip install matplotlib numpy
   ```
   
   Or using a requirements file:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

### Full application (recommended)

1. **Run the full Tkinter application**:
   ```bash
   python app_main.py
   ```

2. **Configure the grid**:
   - Enter rows and columns, then click **Resize**
   - Set obstacle density (e.g. 0.3 for 30%) and click **Random Map**
   - Click **Edit Map** and click cells to toggle walls

3. **Run a search**:
   - Select **Algorithm** (BFS, DFS, UCS, DLS, IDDFS, Bidirectional, GBFS, A*)
   - For GBFS/A*: select **Heuristic** (Manhattan or Euclidean)
   - Check **Dynamic obstacles** for spawning + re-planning
   - Click **Run Search**

4. **View metrics**: Nodes Visited, Path Cost, Execution Time appear below the grid

### Console application

1. **Run the simpler console app**:
   ```bash
   python main.py
   ```

2. **Choose an algorithm** (1-6):
   - `1` - Breadth-First Search (BFS)
   - `2` - Depth-First Search (DFS)
   - `3` - Uniform-Cost Search (UCS)
   - `4` - Depth-Limited Search (DLS)
   - `5` - Iterative Deepening DFS (IDDFS)
   - `6` - Bidirectional Search

3. **Choose a scenario**:
   - `1` - **Default layout** (start and target separated by a wall column)
   - `2` - **Best case** – Start and Target are adjacent (minimal search)
   - `3` - **Worst case** – Start and Target in opposite corners (maximal search)

4. **Watch the visualization**:
   - Yellow cells = Frontier nodes (in queue/stack)
   - Light teal cells = Explored nodes
   - Green cells = Final path (labeled with "0")
   - Red cells = Static obstacles

---

## 📁 Project Structure

```
AI-PathFinder/
│
├── main.py                 # Main entry point and algorithm selector
├── grid_env.py            # Grid environment and cell management
├── view_gui.py            # GUI visualization using Matplotlib
├── search_utils.py        # Utility functions (path reconstruction, obstacle spawning)
│
├── search_bfs.py          # Breadth-First Search implementation
├── search_dfs.py          # Depth-First Search implementation
├── search_ucs.py          # Uniform-Cost Search implementation
├── search_dls.py          # Depth-Limited Search implementation
├── search_iddfs.py        # Iterative Deepening DFS implementation
├── search_bidirectional.py # Bidirectional Search implementation
├── search_gbfs.py         # Greedy Best-First Search implementation
├── search_astar.py        # A* Search implementation
├── heuristics.py          # Manhattan and Euclidean heuristics
└── app_main.py            # Full Tkinter application (recommended)
```

---

## Algorithms Implemented

### 1. **Breadth-First Search (BFS)**
- Explores level by level
- Guarantees shortest path (in terms of steps)
- Uses a queue (FIFO)

### 2. **Depth-First Search (DFS)**
- Explores as deep as possible before backtracking
- Uses a stack (LIFO)
- May not find optimal path

### 3. **Uniform-Cost Search (UCS)**
- Explores nodes with lowest cost first
- Uses a priority queue
- Guarantees optimal path when all step costs are equal

### 4. **Depth-Limited Search (DLS)**
- DFS with a maximum depth limit
- Prevents infinite loops
- May fail if goal is beyond depth limit

### 5. **Iterative Deepening DFS (IDDFS)**
- Combines BFS and DFS benefits
- Runs DLS with increasing depth limits
- Guarantees optimal solution

### 6. **Bidirectional Search**
- Searches from both start and goal simultaneously
- Meets in the middle

### 7. **Greedy Best-First Search (GBFS)**
- Uses f(n) = h(n) only (heuristic)
- Heuristics: Manhattan or Euclidean distance

### 8. **A* Search**
- Uses f(n) = g(n) + h(n)
- Heuristics: Manhattan or Euclidean distance

### Heuristic Functions
- **Manhattan Distance**: D = |x1 - x2| + |y1 - y2|
- **Euclidean Distance**: D = sqrt((x1 - x2)^2 + (y1 - y2)^2)

---

## GUI Legend

- **Green** = Visited path (final route from S to T)
- **Yellow** = Frontier (nodes in queue/stack waiting to be explored)
- **Light Teal** = Expanded/Explored nodes
- **Red** = Static obstacles (walls)
- **Numbers** = Visit order (when each cell was first discovered)

---

## ⚙️ Configuration

### Adjusting Animation Speed
Edit `main.py`:
```python
pause = 0.15  # Seconds between frames (lower = faster)
```

### Changing Grid Size
Edit `main.py`:
```python
grid = Grid(rows=8, cols=8)  # Change to desired dimensions
```

---

## 🐛 Troubleshooting

**Issue**: `ModuleNotFoundError: No module named 'matplotlib'`
- **Solution**: Run `pip install matplotlib numpy`

**Issue**: GUI window doesn't appear
- **Solution**: Ensure you're running Python with GUI support (not headless mode)

**Issue**: "No path found" message appears
- **Solution**: This is expected when obstacles completely block all paths. Try reducing obstacles or adjusting grid layout.

---

## Screenshots

<img width="1916" height="953" alt="image" src="https://github.com/user-attachments/assets/8d26dc6f-8e9d-4bed-8719-13a8403a3306" />


---

## Author

Muhammad Anass Khan

---

## 📝 License

This project is part of an academic assignment. Use responsibly.

---

## Acknowledgments

- Matplotlib for visualization capabilities
- NumPy for efficient grid operations
- Course instructors for algorithm specifications

---

## 📚 References

- Russell, S., & Norvig, P. (2020). *Artificial Intelligence: A Modern Approach* (4th ed.). Pearson.

---

**Made with ❤️ for AI Pathfinding Visualization**

