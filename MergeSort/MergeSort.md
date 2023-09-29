## What is Merge Sort?
Merge Sort는 **Divide-and-Conquer(분할 정복)** 알고리즘의 종류 중 하나이다.

## Procedure of Merge Sort
1. 데이터를 2개의 부분 배열로 나눔 **(Divide)**
2. 더이상 나누지 못하는 부분 배열끼리 정렬 **(Conquer)**
3. 정렬된 부분 배열을 합침 **(Combine)**

![MergeSort](./Images/MergeSortTutorial.png)

## Pros and Cons

- Pros
1. Merge Sort는 다음과 같은 시간 복잡도를 보장한다. $$O(nlogn)$$
2. 따라서 Best case와 Worst case 모두 같은 시간복잡도를 보장한다.

- Cons
1. 단, Merge Sort는 추가적인 공간을 요구하므로 공간 복잡도는 증가한다.
2. 따라서 여유 공간이 부족한 경우, Merge Sort를 이용하지 않고 그때는 Quick Sort로 대체한다.

## Function
```c
void MergeSort(int* arr, int l, int r) {
    int mid = (l + r) / 2;
    if(l < r) {
        MergeSort(arr, l, mid);
        MergeSort(arr, mid+1, r);
        Merge(arr, l, mid, r);
    }

}
```

```c
void Merge(int* arr, int l, int mid, int r) {
    int i = l;
    int j = mid+1;
    int k = l;

    while(i <= mid && j <= r) {
        if(arr[l] <= arr[j]) Sorted[k++] = arr[l++];
        else Sorted[k++] = arr[j++];
    }

    if(l > mid) {
        for(int t=j; t<=r; t++) Sorted[k++] = arr[t];
    } else {
        for(int t=i; t<=mid; t++) Sorted[k++] = arr[t];
    }

    for(int t=l; t<=r; t++) arr[t] = Sorted[t];
}
```