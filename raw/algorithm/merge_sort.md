# Merge Sort

## 부제목
분할 정복 기반 O(n log n) 정렬 알고리즘

## 한 줄 정의
Merge Sort는 배열을 절반으로 분할하고 재귀적으로 정렬한 뒤 병합(merge)하는 분할 정복 정렬이다.

## 알고리즘 구현
```java
void mergeSort(Element[] E, int first, int last) {
    if (first < last) {
        int mid = (first + last) / 2;
        mergeSort(E, first, mid);
        mergeSort(E, mid+1, last);
        merge(E, first, mid, last);
    }
}
```
## 복잡도 분석

* Best: `O(n log n)` / Space: `O(n)`
* Average: `O(n log n)` / Space: `O(n)`
* Worst: `O(n log n)` / Space: `O(n)`

점화식: `T(n) = 2T(n/2) + O(n)` → Master Theorem Case 2 → `Θ(n log n)`

## 강의자료 출처

* CH04.pdf — Sorting, pp.10–15
