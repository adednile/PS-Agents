## Question 2: Directed Graph, Search Tree & Abstraction
### 2.1 Concept of Abstraction
In AI problem formulation, **abstraction** simplifies the real world by stripping away non-essential micro-details (such as individual potholes, street lights, speed bumps, or fuel stops) \[1, 4\]. The search space is defined strictly by treating **towns/cities as states (nodes)** and **highway segments as actions/edges** \[1, 5\].
### 2.2 Directed Graph of Kenya's Highway Network
| From Node (Town) | To Node (Town) | Highway Segment | Distance (km) |
| :---- | :---- | :---- | :---- |
| Nairobi | Naivasha | Nairobi–Nakuru Highway (A104) | \~90 km |
| Naivasha | Nakuru | Rift Valley Highway (A104) | \~70 km |
| Nakuru | Kericho | Mau Summit–Kericho Road (B1) | \~80 km |
| Kericho | Kisumu | Kericho–Kisumu Highway (B1) | \~85 km |
| Nakuru | Eldoret | Nakuru–Eldoret Highway (A104) | \~130 km |
| Eldoret | Kisumu | Eldoret–Kisumu Highway (A104/B1) | \~120 km |
### 2.3 Search Tree Expansion (Initial State: Nairobi → Goal State: Kisumu)
Level 0 (Initial State):

└── Nairobi \[Cost: 0 km\]

    ├── Naivasha \[Cumulative Cost: 90 km\]

    │   └── Nakuru \[Cumulative Cost: 160 km\]

    │       ├── Kericho \[Cumulative Cost: 240 km\]

    │       │   └── Kisumu \[GOAL STATE\] \[Cumulative Cost: 325 km\]

    │       └── Eldoret \[Cumulative Cost: 290 km\]

    │           └── Kisumu \[GOAL STATE\] \[Cumulative Cost: 410 km\]