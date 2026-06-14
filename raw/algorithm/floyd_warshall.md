# Floyd-Warshall Algorithm

## 부제목
DP 기반 전체 쌍 최단 경로 알고리즘

## 한 줄 정의
Floyd-Warshall은 동적 프로그래밍을 사용하여 가중 방향 그래프의 모든 정점 쌍(all-pairs) 사이의 최단 경로를 구하는 알고리즘이다.

## 핵심 아이디어
정점을 1…n으로 번호 매기고, 중간 경유 정점을 1부터 k까지 점진적으로 추가하며 최단 거리를 갱신한다.

```text
FloydWarshall(W, n):
  D⁰ = W
  for k = 1 to n:
    for i = 1 to n:
      for j = 1 to n:
        D^k[i,j] = min(D^(k-1)[i,j],
                       D^(k-1)[i,k] + D^(k-1)[k,j])

```

## 복잡도

* 시간 복잡도: `O(V³)`
* 공간 복잡도: `O(V²)`

## 강의자료 출처

* CH09.pdf — Transitive Closure, All-Pairs Shortest Paths
