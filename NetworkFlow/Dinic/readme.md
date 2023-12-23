### Dinic Algotrithm ###

**prev : https://github.com/2e2guk/Algorithm/tree/main/NetworkFlow/Edmonds-karp**

-> Dinic 알고리즘은, Edmonds-Karp 알고리즘에서, 증가 경로를 찾는 방식을 최적화했던 것에 한 술 더 떠서 최적화한다. 약간 축지법? 느낌..? 묶어서 간다..? 느낌이다. 자세히 알아보자. 

일단, 지난번 글에서 Edmonds-karp 알고리즘은, Residual Grpah 상에서 증가 경로를 찾았다면, Dinic 알고리즘은, **Level Graph** 상에서 증가 경로를 찾는다. Level Graph에 대해 알아보자. 

### Level Graph ###

-> Level Graph는, 다음의 두 가지 조건을 만족하는, Flow Network의 부분 그래프이다. 

**level[i]를, i번 정점으로 도달하기 위해, 출발점(소스)에서 거쳐야 하는 간선의 수**라고 정의한다. 

1. Level Graph 상의 간선의 **잔여 용량 > 0** 이다. 

2. Level Graph 상의 정점 u -> v로의 방향 간선 (u, v)에 대해, **level[v] == level[u]+1** 이다. 
