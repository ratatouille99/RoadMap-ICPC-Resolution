# [Ciclically rotate an array by one](https://practice.geeksforgeeks.org/problems/cyclically-rotate-an-array-by-one2614/1)
```c++
void rotate(int arr[], int n)
{
    int aux{}, temp{};
    
    aux = arr[0];//1
    arr[0] = arr[n-1];//5,
    
    for(int i = 1;i < n; i++){
        temp = arr[i];//3
        arr[i] = aux;//2 = 1
        aux = temp;//2
    }
}
```
