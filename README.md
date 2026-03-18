#  Dijkstra’s Algorithm on Indian Cities Road Network

##  Project Overview

This project implements **Dijkstra’s Algorithm (Uniform-Cost Search)** to compute the shortest path between cities in India using real-world road distance data.

The dataset is sourced from a Kaggle discussion related to route planning and contains city-to-city distance information in CSV format.

Dijkstra’s algorithm is widely used in:

* GPS navigation systems
* Network routing
* Logistics and transportation

---

##  Algorithm Used

We use **Dijkstra’s Algorithm**, a greedy search algorithm that finds the shortest path from a source node to all other nodes in a weighted graph.

### Key Idea:

* Always expand the node with the **lowest cumulative cost**
* Update distances to neighboring nodes if a shorter path is found

---

##  Dataset

Dataset source:
 https://www.kaggle.com/datasets/kbdharun/a-star-algorithm-route-planning-dataset

###  Dataset Structure

The dataset represents a **graph of cities**, where:

* Each row is a connection (edge)
* Cities are nodes
* Distance is the edge weight

Typical CSV format:

```
source,destination,distance
Delhi,Mumbai,1400
Mumbai,Bangalore,980
Bangalore,Chennai,350
```

Such datasets model road networks as graphs, where distances between cities act as weights for shortest-path algorithms. ([Scribd][1])

---

##  Project Structure

```
dijkstra-india/
│
├── main.py                         # Dijkstra implementation
├── india_cities_distances.csv     # Dataset
└── README.md                      # Documentation
```

---

##  Requirements

* Python 3.x
* No external libraries required (uses built-in modules only)

---

##  How to Run the Project

### 1. Clone the Repository

```
git clone https://github.com/your-username/dijkstra-india.git
cd dijkstra-india
```

---

### 2. Add Dataset

Download the dataset from Kaggle and place it in the project folder:

```
india_cities_distances.csv
```

---

### 3. Run the Code

```
python main.py
```

---

### 4. Input Example

```
Enter starting city: Delhi
```

---

### 5. Output Example

```
Shortest distances from Delhi:

Mumbai: 1400 km
Ahmedabad: 950 km
Bangalore: 2380 km
```

---

## Code Explanation

### 1. Graph Construction

* The CSV file is read using `csv.DictReader`
* A graph is built using an adjacency list:

  ```
  graph[city] = [(neighbor, distance)]
  ```

---

### 2. Priority Queue

* Uses `heapq` to always pick the node with the **lowest distance**

---

### 3. Distance Tracking

* Initialize all distances to infinity
* Update when a shorter path is found

---

### 4. Algorithm Flow

1. Start from source city
2. Visit nearest unvisited node
3. Update neighbors
4. Repeat until all nodes processed

---

##  Features

* Works with real-world datasets
* Efficient shortest-path computation
* Scalable to large city networks
* Simple and clean implementation

---

##  Limitations

* Does not return the actual path (only distance)
* Assumes all distances are positive
* Dataset quality affects accuracy

---

## References

* Dijkstra, E. W. (1959). *A note on two problems in connexion with graphs*
* Kaggle dataset (linked above)




