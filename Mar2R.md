# Mar 2

- Merge sort
```java
private void doMergeSort(int lowerIndex, int higherIndex) {
     
    if (lowerIndex < higherIndex) { // Base case
        int middle = lowerIndex + (higherIndex - lowerIndex) / 2; // Get midpoint
        
        // Below step sorts the left side of the array using the middle
        doMergeSort(lowerIndex, middle);
        
        // Below step sorts the right side of the array using the middle
        doMergeSort(middle + 1, higherIndex);
        
        // Now merge both sides
        mergeParts(lowerIndex, middle, higherIndex);
    }
}

private void mergeParts(int lowerIndex, int middle, int higherIndex) {
    for (int i = lowerIndex; i <= higherIndex; i++) {
        // Copy all the contents of the input array to a temporary array
        tempMergArr[i] = array[i];
    }
    int i = lowerIndex;
    int j = middle + 1;
    int k = lowerIndex;
    while (i <= middle && j <= higherIndex) {
        if (tempMergArr[i] <= tempMergArr[j]) {
            array[k] = tempMergArr[i]; 
            i++; // Sentinel 
        } else {
            array[k] = tempMergArr[j];
            j++; // Sentinel
        }
        k++;
    }
    while (i <= middle) {
        array[k] = tempMergArr[i];
        k++;
        i++;
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
