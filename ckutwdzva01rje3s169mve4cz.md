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
- If you know the range of numbers present in the data to be sorted, then Counting Sort is a better than the rest of the above specified algorithms.
- **Time Complexity** : 
        Best Case : O(N) - When all the array elements are same.
        Worst Case: O(N*N) -  When the range is too complex.
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



That's it for now. Meet you in the next article. ❤
Do check out my other blogs. I'm sure you'll love them ! 🦄

வாழ்க தமிழ் ! வளர்க தமிழினம் ! 🟥🟨