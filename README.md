## **MODULARITY ON KARATE CLUB GRAPH**

This project implements a multi-community detection algorithm using recursive spectral modularity partitioning on Zachary’s Karate Club graph, along with visualizations and network metric tracking across iterations.

The algorithm extends the standard two-way spectral split into recursive bisection, enabling detection of multiple communities.
At each iteration, the graph is split based on the leading eigenvalue/eigenvector of the modularity matrix, and the process continues until no further meaningful split is possible.


 **DISCUSSION**

Using the Zachary's Karate Club graph (Nodes 0 and 33 represent the two main leaders), the metric evolution plots provide insight into which nodes maintain their structural importance despite the community restructuring:

- Node 0 (The Instructor) and Node 33 (The Administrator): These nodes consistently remain high in Degree Centrality and Closeness Centrality. Their high Degree reflects their roles as major hubs, and their high Closeness shows their efficient access to all parts of the network, which is generally unaffected by internal community splits.

- Betweenness Centrality: This metric is highly sensitive to the initial split. Nodes that lie on the boundary between the first two major communities (the "bridges") will initially have the highest betweenness. As the network is partitioned, nodes that act as internal bridges within a sub-community will see their betweenness rise, while nodes acting as bridges between groups that have already stopped splitting will see their betweenness stabilize or drop. Node 0, in particular, often maintains high Betweenness due to its critical position connecting sub-factions.

- Clustering Coefficient: The Clustering Coefficient generally remains stable, as it measures local cohesion (triangles). Its value is less affected by large-scale spectral splits unless the split radically changes a node's local neighborhood degree, which is not the case when measuring on the full graph $G$.

In summary, nodes 0 and 33 demonstrate robust centrality (Degree and Closeness) throughout the recursive bisection process, confirming their role as the primary, stable structural leaders of the network.

