# Directed Graph

- $In(V_{i})$ : set of vertices that point to it

- $Out(V_{i})$ : set of vertices that vertec $V_{i}$ points to

- score of vertex $V_{i}$

  $S(V_{i})=(1-d)+d*sum_{j in In(V_{i})} frac{1}{|Out(V_{j})|}S(V_{j})$
  
  where d is damping factor (=0.85)
  
# Undirected Graph

The out-degree of a vertex is equal to the in-degree of the vertex.
(The convergence curves for directed and undirected graphs practically overlap)

# Weighted Graph

It may include multiple or partial links between the units(vertices) that are 
extracted from text.

- weighted score of vertex $V_{i}$

  $WS(V_{i}) = (1-d)+d*sum_{V_{j} in In(V_{i})} frac{w_{ji}}{sum_{V_{k} in Out(V_{j})} w_{jk}} WS(V_{j})$
  
- $frac{w_{ji}}{sum_{V_{k} in Out(V_{j})}$

  Out(V_{j}) edge의 weights 중 V_{i} edge에 해당하는 weight 비율

# Text as a Graph

- V_{i} : word / sentence / etc.

- w_{ij} : lexical or semantic relations / contextual overlap / etc.
