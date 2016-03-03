# Mar 2

- Merge sort
```java
mergeSort(int[] arr) {
  mergeSortRec(arr, 0, arr.length-1);
}

mergeSortRec(int[] arr, int firstIndex, int lastIndex) {
  if(firstIndex == lastIndex) {
    return;
  }
  mid = (firstIndex + lastIndex)/2;
  mergeSortRec(arr, firstIndex, mid);
  mergeSortRec(arr, mid+1, lastIndex);
  merge(arr, firstIndex, mid, mid+1, lastIndex);
}

merge(int[] arr, int leftFirst, int leftLast, int rightFirst, int rightLast) {
  int[] temp = new int[rightLast-leftFirst+1];
  int indexLeft = leftFirst;
  int indexRight = rightFirst;
  int index = 0;

  while(indexLeft <= leftLast && indexRight <= rightLast) {
    if(arr[indexLeft] < arr[indexRight]) {
      temp[index] = arr[indexLeft];
      ++indexLeft;
    } else {
      temp[index] = arr[indexRight];
      ++indexRight;
    }
    ++index
  }
  for(int i=indexLeft; i<leftLast; ++i) {
    temp[index] = arr[i];
    ++index;
  }
  for(int k=indexRight; k<rightLast; ++k) {
    temp[index] = arr[k];
    ++index;
  }
  for(int j=leftFirst; j<temp.length; ++j) {
    arr[j] = temp[j];
  }
}
```
- Quicksort
```java
int partition(float[] A, int left, int right, int pivot) {
  float temp = A[pivot];
  A[pivot] = A[right];
  A[right] = temp;

  while(left < right) {
    while(A[left] < A[pivot]) {
      left++;
    }
    while(right > left && A[right] > A[pivot]) {
      right--;
    }
    if(right > left) {
      temp = A[left];
      A[left] = A[right];
      A[right] = temp;
    }
  }
  return left;
}

quickSort(float A[], int left, int right) {
  int pivot = findPivot(A, left, right);
  int index = partition(A, left, right, pivot);
  if (index - left > 1) {
    quickSort(A, left, index-1);
  }
  if (right - index > 1) {
    quickSort(A, index-1, right);
  }
}
```
