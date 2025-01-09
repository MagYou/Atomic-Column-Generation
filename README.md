# Resource Constrained Shortest Path (RCSP) Instances

This repository contains instances for the **Resource Constrained Shortest Path (RCSP)** problem, which is used in optimization and network design. The instances are divided into **Grid instances**, **SNDLIB instances** and **Zoo topology Instances**, with each set containing both **Feasible** and **Infeasible** cases.

## Instance Categories
1. **Grid Instances**: These instances represent grid-based network structures.
2. **SNDLIB & Zoo topology Instances**: These instances are based on real-world networks and are from the **SNDLIB (Survivable Network Design Library)** and **Zoo topology**.

Each instance is further categorized into:
- **Feasible Instances**: These instances have solutions that satisfy all constraints (resource limits).
- **Infeasible Instances**: These instances do not have feasible solutions due to the violation of resource constraints.

## Instance Format

Each instance is represented by a file with multiple headers that define the parameters and constraints of the RCSP problem.

### 1. **First Header**
- **link_source**: The source node of the link.
- **link_destination**: The destination node of the link.
- **cost**: The cost associated with the link.
- **metric_1 to metric_6**: These represent various resource metrics (e.g., bandwidth, time, energy, etc.) associated with the link. The exact definition of each metric depends on the instance and the resource being modeled.

### 2. **Second Header**
- **source**: The source node of the path.
- **destination**: The destination node of the path.

This header indicates the nodes between which we need to find the shortest path while respecting resource constraints.

### 3. **Third Header**
- **lower_bound**: The lower bound of the resource constraint for a specific metric.
- **upperbound**: The upper bound of the resource constraint for that metric.

These values define the feasible range for each metric. The path found must satisfy these bounds for each metric (e.g., the total bandwidth used should lie within the range specified by the lower and upper bounds).

### 4. **Fourth Header**
- **included_node(s)**: This is a list of nodes that must be included in the feasible path.

These nodes are required to be part of any solution. If an instance is infeasible, it might be due to the inability to include these mandatory nodes while respecting the resource constraints.

