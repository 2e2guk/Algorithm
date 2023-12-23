### Dinic Algotrithm ###

**prev : https://github.com/2e2guk/Algorithm/tree/main/NetworkFlow/Edmonds-karp**

-> Dinic 알고리즘은, Edmonds-Karp 알고리즘에서, 증가 경로를 찾는 방식을 최적화했던 것에 한 술 더 떠서 최적화한다. 약간 축지법? 느낌..? 묶어서 간다..? 느낌이다. 자세히 알아보자. 

일단, 지난번 글에서 Edmonds-karp 알고리즘은, Residual Grpah 상에서 증가 경로를 찾았다면, Dinic 알고리즘은, **Level Graph** 상에서 증가 경로를 찾는다. Level Graph에 대해 알아보자. 

### Level Graph ###

-> Level Graph는, 다음의 두 가지 조건을 만족하는, Flow Network의 부분 그래프이다. 

**level[i]를, i번 정점으로 도달하기 위해, 출발점(소스)에서 거쳐야 하는 간선의 수**라고 정의한다. 

1. Level Graph 상의 간선의 **잔여 용량 > 0** 이다. 

2. Level Graph 상의 정점 u -> v로의 방향 간선 (u, v)에 대해, **level[v] == level[u]+1** 이다. 

그리고, Dinic 알고리즘은, **Level Grpah를 구성했는데, 소스-> 싱크로 도달할 수 없을 때**까지, 

이렇게 구성한 **Level Graph 상에서, 최대 유량을 찾아 흘리고, 다시 Level Graph를 구성하고... 를 반복**한다.  

그러면, Level Graph가 의미하는 바는 뭘까? 

Level Graph는, 소스->싱크로의 최단 거리(거쳐가는 간선의 최소 개수)를 D로 고정했을 때, **거리 D짜리, 증가 경로의 합집합** 을 의미한다!!

Edmonds-Karp 알고리즘은, 거리 D까리 증가 경로를 하나 찾고, 유량을 흘리고, 또 하나 찾고, 유량을 흘리고, 이제 더 이상 D짜리 증가 경로를 찾을 수 없다면 D+1짜리 증가 경로를 찾고..를 반복했다면, 

Dinic 알고리즘은, 거리 D짜리 증가 경로의 합집합을 Level Graph로 구성하고, 이 Level Graph 상에서 최대 유량을 찾아 흘려서, **유량을 한꺼번에 흘린다**. 

그리고 길이 D+1짜리 Level Grpah를 구성하고.. 를 반복한다. 이렇게, 

**기존의 증가 경로를 하나하나 찾아서, 유량도 하나하나 찾아서 흘리던 과정 -> 한꺼번에 증가 경로를 모두 찾고, 유량은 한 번만 흘리는** 방식으로 최적화한다. 

물론, 전체 과정에서 유량을 딱 한번만 흘리는 것은 아니고, **길이 D짜리 Level Graph에서 한번, 길이 D+1짜리 Level Graph에서 한번....** 이렇게 흘린다.

그리고, **각 길이의 Level Graph에서의 최대 유량을, Blocking Flow** 라고 한다. 

이제 서두에서 말한, 축지법, 묶어서 간다.. 라는 말이 무슨 말인지 이해가 되었기를 바란다.

### Dinic algorithm ###

1. Level Graph 구성.

2. 현재 Level Graph에서 Blocking Flow 찾아 흘리기

3. Level Graph를 구성했는데, 소스->싱크로 도달이 불가능할 때까지, 1, 2번 과정 반복.

**Level Graph 구성은 BFS기반, Blocking Flow를 찾는 과정은, DFS기반** 이다. 

그래서, Dinic 알고리즘은, **BFS, DFS를 섞어서 사용한다.** 이 Dinic 알고리즘의 시간 복잡도는 최악의 경우 **O(V^2E)**이다. 근데, 실제로는 **훨씬 빨리 작동한다.**
