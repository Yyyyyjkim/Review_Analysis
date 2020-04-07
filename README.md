# review summary using text-rank

## Directed Graph

- $In(V_{i})$ : set of vertices that point to it

- $Out(V_{i})$ : set of vertices that vertex $V_{i}$ points to

- Score of vertex $V_{i}$

  $S(V_{i})=(1-d) + d*sum_{j in In(V_{i})} frac{1} {|Out_{V_{j}}|} S(V_{j})$
  
  d : damping factor(=0.85)

  V_{i}의 score는 node V_{i}로 들어오는 각 node의 score를 edge 수로 나눈 값
  
## Undirected Graph

The out-degree of a vertex is equal to the in-degree of the vertex.
(edge의 방향이 없다.)

The convergence curves for directed and undirected graphs practically overlap.

## Weighted Graph

It may include multiple or partial links between the units(vertices) that are extracted from text.

- Weighted Score of V_{i}

  $WS(V_{i})=(1-d)+d*sum_{V_{j} in In(V_{i})} frac{w_{ji}} {sum_{V_{k} in Out(V_{j})} w_{jk}} WS(V_{j})$
  
  V_{j}를 나가는 edge의 weights 중 V_{i}로 향하는 edge에 해당하는 weight의 비율
  
## Text as a Graph

- V_{i} : word / sentence / etc.

- W_{ij} : lexical or semantic relations / contextual overlap / etc

## TextRank for Keyword Extraction

Two vertices are connected if their corresponding lexical units co-occur within a window of maximum N words,
where N can be set anywhere from 2 to 10 words.

## TextRank for Sentence Extraction

The overlap of two sentences can be determined simply as the number of common tokens between the 
lexical representations of the two sentences.

To avoid prompting long sentences, use a normalization filter and devide the content overlap of 
tow sentences with the length of each sentence.

- Similarity

  S(s_{i},s_{j}) = frac{|\{w_{k}|w_{k} in s_{i} & w_{k} in s_{j}}\}|} {log(|N_{i}|) + log(|N_{j}|)}
  
  두 문장에 공통으로 속해있는 단어의 수 / sum(log(각 문장의 길이))
