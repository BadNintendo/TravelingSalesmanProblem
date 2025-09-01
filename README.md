# 🧭 TSP Visualizer & Optimizer [TSP.py](./TSP.py)

A scratch-built, axis-separated Traveling Salesman Problem (TSP) solver with real-time 2D/3D animation using Matplotlib. This implementation avoids bundled heuristics and prioritizes semantic clarity, reproducibility, and extensibility.

## 🚀 Features

- Nearest-neighbor path construction
- 2-opt optimization for path refinement
- Memoized Euclidean distance calculation
- Real-time animated rendering (2D or 3D auto-detect)
- Interactive zoom and manual step-through
- Validator-ready output with timing and distance metrics

## 📦 Requirements

```bash
pip install matplotlib
```

## 🧠 Algorithm Overview

| Phase            | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `nearest()`      | Builds initial path using greedy nearest-neighbor logic                     |
| `optimize()`     | Applies 2-opt swaps to reduce total path distance                           |
| `dist()`         | Memoized Euclidean distance between cities                                  |
| `render()`       | Dynamically draws path in 2D or 3D space with zoom and pan support          |
| `update()`       | Animation frame handler for progressive path rendering                      |
| `zoom_handler()` | Mouse scroll zooms in/out and pans viewport                                 |
| `click_handler()`| Mouse click manually advances animation frame                               |

## 🧮 Usage

Replace `check_array = cities` with your own list of city dictionaries:

```python
cities = [
    {'name': 'A', 'x': 0, 'y': 0},
    {'name': 'B', 'x': 1, 'y': 1},
    {'name': 'C', 'x': 2, 'y': 0},
    # Optional 3D: add 'z' key
]
```

Then run the script:

```bash
python tsp_visualizer.py
```

## 📊 Output

```text
Initial Distance: 123.456
Initial Solution Time (ms): 4.321
Optimized Distance: 98.765
Optimization Time (ms): 2.109
Sorted Path Length: 11
Start: {'name': 'A', 'x': 0, 'y': 0}
Penultimate: {'name': 'K', 'x': 5, 'y': 2}
End: {'name': 'A', 'x': 0, 'y': 0}
```

## 🎥 Demo

- Auto-detects 2D or 3D based on presence of `'z'` key
- Colors each segment using Tableau palette
- Click to manually advance frames
- Scroll to zoom and pan

## 🧩 Extensibility

- Swap in alternate heuristics or optimization strategies
- Extend `dist()` for geodesic or weighted metrics
- Integrate with external validators or lexicons
