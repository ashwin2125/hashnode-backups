## Sorting Algorithms and it's Time Complexities - Simplified !

# Searching Algorithms and it's Time Complexities

### Bubble Sort :

- Take larger element to the end, by reportedly swapping the adjacent elements.
- **Time Complexity** : 
        Best Case : O(N) - When the array is sorted
        Worst Case: O(N*2) - When the array is reverse sorted.
- **Bubble Sort - Algorithm : **

   ```
void bubbleSort(int *arr, int n){
    for (int i = 1; i <= n - 1; i++){
        for (int j = 0; j <= n - i - 1; j++){
            if (arr[j] > arr[j + 1]){
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}
``` 

### Insertion Sort :
- Insert the element in the correct position in a sorted part.
- **Time Complexity** : 
        Best Case : O(N) - When the array is sorted
        Worst Case: O(N*2) - When the array is reverse sorted.    
- **Insertion Sort - Algorithm : **

   ```
void insertionSort(int *arr, int n){
    for(int i=1;i<=n-1;i++){
        int current = arr[i];
        int prev = i - 1;
        while(prev>=0 && arr[prev]>current){
            arr[prev+1] = arr[prev];
            prev-=1;
        }
        arr[prev+1] = current;
    }
}
``` 

### Selection Sort :
- Repeatedly find the minimum element from the unsorted part and putting it at the beginning.
- **Time Complexity** : 
        Best Case : O(N*2)
        Worst Case: O(N*2)
- **Selection Sort - Algorithm : **

   ```
void selectionSort(int *arr, int n){
    for(int position = 0;position<=n-2;position++){
        int currentElement = arr[position];
        int minPosition = position;
        for(int j = position;j<n;j++){
            if(arr[j]<arr[minPosition]){
                minPosition = j;
            }
        }
        swap(arr[minPosition],arr[position]);
    }
    for(int i=0;i<n;i++){
        cout<<arr[i]<<" ";
    }
}
``` 

### Quick Sort :
- One of the fastest sorting algorithms which is widely used everywhere where 'stability' is not a priority. 
- Quick Sort is a divide and conquer algorithm and also an in-place sorting algorithm which doesn't require any extra storage.

- **Time Complexity** : 
        Best Case : O(NLogN) - When the random pivot is the middle element.
        Worst Case: O(N*N) - When the random pivot is greatest/smallest element

- **Quick Sort - Algorithm : **

   ```
int partition (int arr[], int low, int high) 
{ 
    int pivot = arr[high];     
    int i = (low - 1);  
  
    for (int j = low; j <= high- 1; j++) 
    { 
        if (arr[j] <= pivot) 
        { 
            i++;    
            swap(&arr[i], &arr[j]); 
        } 
    } 
    swap(&arr[i + 1], &arr[high]); 
    return (i + 1); 
}
void quickSort(int arr[], int low, int high) 
{ 
    if (low < high) 
    {
        int pi = partition(arr, low, high); 
  
        quickSort(arr, low, pi - 1); 
        quickSort(arr, pi + 1, high); 
    } 
} 
``` 

### Counting Sort :
- If you know the range of numbers present in the data to be sorted, then Counting Sort is a better than the rest of the above specified algorithms.
- **Time Complexity** : 
        Best Case : O(N) - When all the array elements are same.
        Worst Case: O(N+K) -  When the range is too complex.
- **Counting Sort - Algorithm : **

   ```
vector<int> countingSort(vector<int> arr){
    //FindLargest&SmallestElementOfArray
    int n = arr.size();
    int largest = *max_element(arr.begin(), arr.end());
    //Frequency Vector;
    vector<int> freq(largest+1,0);
    //Update the freq vector:
    for(int x:arr){
        freq[x]++;
    }
    //Put Back the elements from freq to original array
    int j=0;
    for(int i=0;i<largest;i++){
        while(freq[i]>0){
            arr[j] = i;
            freq[i]--;
            j++;
        }
    }
    return arr;
}``` 

### Merge Sort :
- Divide and Conquer Algorithm which uses both recursive and non-recursive approaches to sort the data.
- Stable algorithm which also requires extra memory space for its operations - O(N)


- **Time Complexity** : 
        Best Case : O(NLogN) - As merge sort always performs same number of operations
        Worst Case: O(NLogN) - so, the Best and Worst case is always O(NLogN)

- **Merge Sort - Algorithm : **

```
void mergesort(int A[],int size_a,int B[],int size_b,int C[])
{
     int token_a,token_b,token_c;
     for(token_a=0, token_b=0, token_c=0; token_a<size_a && token_b<size_b; )
     {
          if(A[token_a]<=B[token_b])
               C[token_c++]=A[token_a++];
          else
               C[token_c++]=B[token_b++];
      }
      
      if(token_a<size_a)
      {
          while(token_a<size_a)
               C[token_c++]=A[token_a++];
      }
      else
      {
          while(token_b<size_b)
               C[token_c++]=B[token_b++];
      }

}
``` 



That's it for now. Meet you in the next article. ❤
Do check out my other blogs. I'm sure you'll love them ! 🦄

வாழ்க தமிழ் ! வளர்க தமிழினம் ! 🟥🟨