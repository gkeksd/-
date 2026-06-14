# Binary Search

## 부제목
정렬된 배열에서 O(log n)에 원소를 탐색

## 한 줄 정의
Binary Search는 정렬된 배열에서 탐색 범위를 절반씩 줄여가며 목표 원소를 찾는 알고리즘이다.

```java
int binarySearch(int[] E, int n, int K) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (E[mid] == K) return mid;
        else if (E[mid] < K) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```
## 복잡도

W(n) = ⌊log₂ n⌋ + 1 → `O(log n)`
점화식: `T(n) = T(n/2) + O(1)`

## 강의자료 출처

* CH01.pdf — Searching an Ordered Array
