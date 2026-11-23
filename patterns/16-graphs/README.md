# 16 - Graphs (DFS/BFS)

Status: 🟡 In progress (Day 0/5), cycle started 2026-11-23

## Pattern summary
A graph is nodes plus edges; grids are graphs where each cell connects to its 4 (or 8) neighbours. Recognize it by grids, islands, connected components, "reachable from", or shortest number of steps with unit cost. Use DFS (recursion or stack) to explore everything reachable, and BFS (queue) when you need the shortest path or level-by-level spread. Always track visited cells so each node is processed once.
Complexity: O(V + E) time (grid: O(rows * cols)), O(V) space for visited and the queue/stack.

## Template (generic skeleton)
```python
from collections import deque

DIRS = [(1, 0), (-1, 0), (0, 1), (0, -1)]

def dfs(grid, r, c, visited):
    rows, cols = len(grid), len(grid[0])
    if not (0 <= r < rows and 0 <= c < cols) or (r, c) in visited or grid[r][c] == "0":
        return
    visited.add((r, c))
    for dr, dc in DIRS:
        dfs(grid, r + dr, c + dc, visited)

def bfs(grid, start_r, start_c):
    rows, cols = len(grid), len(grid[0])
    q = deque([(start_r, start_c)])
    visited = {(start_r, start_c)}
    steps = 0
    while q:
        for _ in range(len(q)):          # one BFS level
            r, c = q.popleft()
            for dr, dc in DIRS:
                nr, nc = r + dr, c + dc
                if 0 <= nr < rows and 0 <= nc < cols and (nr, nc) not in visited:
                    visited.add((nr, nc))
                    q.append((nr, nc))
        steps += 1
    return steps
```

## Top 5 study exercises (Day 0)
| # | Problem | LC # | Difficulty | LeetCode link | Video explanation |
|---|---------|------|-----------|---------------|-------------------|
| 1 | Max Area of Island | 695 | Medium | [link](https://leetcode.com/problems/max-area-of-island/) | [NeetCode](https://www.youtube.com/watch?v=iJGr1OtmH0c) |
| 2 | Number of Islands | 200 | Medium | [link](https://leetcode.com/problems/number-of-islands/) | [NeetCode](https://www.youtube.com/watch?v=pV2kpPD66nE) |
| 3 | Clone Graph | 133 | Medium | [link](https://leetcode.com/problems/clone-graph/) | [NeetCode](https://www.youtube.com/watch?v=mQeF6bN8hMk) |
| 4 | Rotting Oranges | 994 | Medium | [link](https://leetcode.com/problems/rotting-oranges/) | [NeetCode](https://www.youtube.com/watch?v=y704fEOx0s0) |
| 5 | Pacific Atlantic Water Flow | 417 | Medium | [link](https://leetcode.com/problems/pacific-atlantic-water-flow/) | [NeetCode](https://www.youtube.com/watch?v=s-VkcjHqkGI) |

## Practice log
| Date | Problem | Difficulty | Time | Memory | Folder |
|------|---------|------------|------|--------|--------|
