# 🚑 Emergency Rescue AI

> **An intelligent emergency route-planning system that helps identify a suitable route from a rescue location to a hospital while considering blocked roads, fire, flood, and traffic conditions.**

---

## 📌 Overview

During emergencies and natural disasters, rescue teams may face blocked roads, floods, fire, and heavy traffic. Selecting a suitable route manually can take valuable time.

**Emergency Rescue AI** is a web-based route-planning system that uses different pathfinding algorithms to calculate a route between a **Rescue Point** and a **Hospital**.

The system provides a visual grid-based emergency map where users can add different road conditions and observe how the selected pathfinding algorithm finds a route.

---

## 🎯 Problem Statement

During emergency situations and natural disasters, roads may be blocked, flooded, affected by fire, or congested with traffic. These conditions can delay rescue operations and make manual route selection difficult.

Therefore, there is a need for an intelligent system that can analyze road conditions and help determine a suitable route from the rescue location to a hospital.

---

## 💡 Proposed Solution

Emergency Rescue AI provides an interactive rescue map where the user can:

- 🚑 Select a Rescue Point
- 🏥 Select a Hospital
- 🚧 Mark blocked roads
- 🔥 Mark fire zones
- 🌊 Mark flood zones
- 🚗 Mark traffic zones
- 🧠 Select a pathfinding algorithm
- 📍 Calculate a rescue route
- 📊 Calculate route distance and cost
- ⚠️ Calculate route risk
- 🎤 Use voice commands

The system dynamically calculates a route based on the selected algorithm and road conditions.

---

## 🧠 Pathfinding Algorithms

The project supports five algorithms:

### 1. A* Algorithm

A* combines the actual path cost with a heuristic distance to the destination.

```text
f(n) = g(n) + h(n)
```

Where:

- `g(n)` = cost from the starting point
- `h(n)` = estimated cost to the destination
- `f(n)` = total estimated cost

---

### 2. Breadth First Search (BFS)

BFS explores the map level by level and can find a path with the minimum number of steps when movement has equal cost.

---

### 3. Depth First Search (DFS)

DFS explores one path deeply before backtracking and trying another path.

---

### 4. Dijkstra's Algorithm

Dijkstra's algorithm finds the minimum-cost path by considering the movement cost of different road conditions.

---

### 5. Greedy Best First Search

Greedy Best First Search selects the next cell based mainly on its estimated distance from the destination.

---

## 🚧 Road Condition Costs

Different road conditions have different movement costs.

| Condition | Cost | Meaning |
|---|---:|---|
| 🟢 Normal Road | 1 | Normal movement |
| 🚗 Traffic | 3 | Increased movement cost |
| 🌊 Flood | 5 | High movement cost |
| 🔥 Fire | 8 | Very high movement cost |
| 🚧 Blocked | ∞ | Cannot be crossed |

This allows weighted algorithms such as **A\*** and **Dijkstra** to consider hazardous conditions while calculating a route.

---

## 🗺️ System Workflow

```text
        START
          │
          ▼
   Select Rescue Point
          │
          ▼
     Select Hospital
          │
          ▼
   Add Road Conditions
          │
          ├── 🚧 Blocked
          ├── 🔥 Fire
          ├── 🌊 Flood
          └── 🚗 Traffic
          │
          ▼
 Select Pathfinding Algorithm
          │
          ▼
     Calculate Route
          │
          ▼
   Analyze Route Cost
          │
          ▼
    Calculate Risk
          │
          ▼
    Display Rescue Route
          │
          ▼
         END
```

---

## 🖥️ Features

### 🚑 Rescue Point

The user can select the location from where the rescue operation starts.

### 🏥 Hospital Selection

The user can select the destination hospital.

### 🚧 Blocked Roads

Blocked cells are treated as unavailable and cannot be used by the pathfinding algorithms.

### 🔥 Fire Zones

Fire zones have a high movement cost, representing dangerous areas.

### 🌊 Flood Zones

Flood zones have increased movement cost to represent difficult movement conditions.

### 🚗 Traffic Zones

Traffic zones have an additional movement cost.

### 📊 Route Analysis

After calculating a route, the system displays:

- Selected algorithm
- Route distance
- Total route cost
- Route risk
- Route status

### 🎤 Voice Command

The system supports basic browser-based voice commands such as:

```text
Find route
Find rescue route
Clear map
```

Voice recognition works best in supported versions of Google Chrome.

---

## 🛠️ Technologies Used

### Frontend

- HTML5
- CSS3
- JavaScript

### Algorithms

- A*
- BFS
- DFS
- Dijkstra
- Greedy Best First Search

### Browser APIs

- Web Speech API

---

## 📂 Project Structure

```text
Emergency-Rescue-AI/
│
├── index.html
│
└── README.md
```

---

## ⚙️ How to Run

### Method 1 — VS Code + Live Server

1. Download or clone the repository.

2. Open the project folder in VS Code.

3. Open:

```text
index.html
```

4. Install the **Live Server** extension in VS Code.

5. Right-click `index.html`.

6. Select:

```text
Open with Live Server
```

7. The application will open in your browser.

---

## 💻 Run Using Git

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Emergency-Rescue-AI.git
```

Move into the project directory:

```bash
cd Emergency-Rescue-AI
```

Then open `index.html` using Live Server.

---

## 🧪 How to Test

### Test 1 — A* Route

1. Select **A\***.
2. Add some blocked roads.
3. Click **Find Rescue Route**.
4. The system calculates a route around blocked cells.

### Test 2 — Fire Zone

1. Select 🔥 Fire Zone.
2. Click several cells.
3. Select A* or Dijkstra.
4. Calculate the route.
5. Fire cells have a higher movement cost.

### Test 3 — Flood Zone

1. Select 🌊 Flood Zone.
2. Add flood cells.
3. Run the pathfinding algorithm.
4. The route calculation considers the additional flood cost.

### Test 4 — Traffic

1. Select 🚗 Traffic Zone.
2. Add traffic cells.
3. Run A* or Dijkstra.
4. The traffic cells increase route cost.

### Test 5 — Blocked Route

1. Select 🚧 Blocked Roads.
2. Create obstacles between the rescue point and hospital.
3. Run the algorithm.
4. The algorithm attempts to find another available path.

---

## 📊 Example

Suppose the route contains:

```text
Normal → Traffic → Flood → Normal
```

The approximate movement cost is:

```text
1 + 3 + 5 + 1 = 10
```

A blocked cell is not included because:

```text
Blocked = ∞
```

---

## 🎨 User Interface

The application provides:

- Dark emergency-response dashboard
- Interactive grid map
- Rescue and hospital markers
- Road-condition visualization
- Algorithm selection
- Route visualization
- Route analysis dashboard
- Responsive interface

---

## 🔮 Future Enhancements

The current system uses a grid-based map for route planning. Future versions can include:

- 🗺️ Real geographic maps
- 📍 GPS-based rescue location
- 🏥 Real hospital locations
- 🚦 Real-time traffic data
- 🌧️ Live flood information
- 🔥 Real-time fire/disaster information
- 🤖 Machine learning-based risk prediction
- ☁️ Cloud database
- 📱 Mobile application
- 🚁 Drone integration
- 🚑 Real-time ambulance tracking
- 🗺️ OpenStreetMap integration
- 🐍 Python backend for advanced AI processing

---

## ⚠️ Limitations

- The current map is a simulated grid rather than a real geographic map.
- Traffic, fire, and flood conditions are manually entered by the user.
- Route distance is measured in grid cells rather than actual kilometers.
- Voice commands depend on browser support.
- The system is a prototype and should not be used as the sole navigation system during real emergencies.

---

## 🌍 Applications

The system can be useful as a prototype for:

- 🚑 Ambulance route planning
- 🚒 Fire rescue operations
- 🌊 Flood rescue
- 🏚️ Disaster management
- 🚨 Emergency response
- 🏥 Hospital emergency routing
- 🚁 Search and rescue planning

---

## 👨‍💻 Project Type

**Academic / College Project**

**Domain:** Artificial Intelligence & Emergency Management

**Project:** Emergency Rescue AI

---

## 📜 License

This project is developed for educational and academic purposes.

You may modify and improve the project according to your requirements.

---

## ⭐ Support

If you find this project useful, you can give the repository a ⭐ on GitHub.

---

### 🚑 Emergency Rescue AI

**Plan smarter. Find routes faster. Support emergency response.**
