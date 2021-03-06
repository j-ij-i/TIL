# Floyd-Warshall Algorithm

- **모든 노드**간의 **최단 경로**를 구하는 알고리즘
- 다익스트라와 달리 음의 간선도 사용 가능하다.
- 시간 복잡도는 **O(n^3)** 으로 다익스트라의 시간복잡도와 동일하다.
- 하지만 인접행렬보다 인접 리스트로 구현 했을 때 시간복잡도가 유리하다.
- 기본적으로 DP 알고리즘의 형태를 가지며 **매우 간단**해서 빨리 짤 수 있는 장점이 있다.

## PseudoCode

```java
Floyd_Warshall(D[][])
 FOR k in 1 -> n
  FOR i in 1 -> n
    FOR j in 1 -> n
      D[i][j] <- min(D[i][k] + D[k][j], D[i][j])
```
