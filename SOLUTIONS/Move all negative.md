# [Move all negative numbers to beginning and positive to end with constant extra space](https://www.geeksforgeeks.org/move-negative-numbers-beginning-positive-end-constant-extra-space/#practice)

# [Alternate positive and negative numbers](https://practice.geeksforgeeks.org/problems/array-of-alternate-ve-and-ve-nos1401/1)
```c++
//User function template for C++
class Solution{
public:

	void rearrange(int arr[], int n) {
	    vector<int>pos, neg, final;
	    
	    for(int i = 0; i < n; i++){
	        if(arr[i] >= 0) pos.push_back(arr[i]);
	        else neg.push_back(arr[i]);
	    }
	    
	    if(pos.size() > 0 && neg.size() > 0){
    	    if(pos.size() > neg.size()){
    	        for(int i = 0; i < neg.size(); i++){
    	            final.push_back(pos[i]);
    	            final.push_back(neg[i]);
    	        }
    	        for(int i = neg.size(); i < pos.size(); i++){
    	            final.push_back(pos[i]);
    	        }
    	    }
    	    
    	    else{
    	        for(int i = 0; i < pos.size(); i++){
    	            final.push_back(pos[i]);
    	            final.push_back(neg[i]);
    	        }
    	        for(int i = pos.size(); i < neg.size(); i++){
    	            final.push_back(neg[i]);
    	        }
    	    }
	    }
	    
	    else{
	        if(pos.size() > 0){
    	        for(int i = 0; i < pos.size(); i++){
    	            final.push_back(pos[i]);
    	        }
    	    }
    	    
    	    else{
    	        for(int i = 0; i < neg.size(); i++){
    	            final.push_back(neg[i]);
    	        }
    	    }
	    }
	    
	    for(int i = 0; i < n; i++) arr[i] = final[i];
	}
};
```

# [Move all negative elements to end](https://practice.geeksforgeeks.org/problems/move-all-negative-elements-to-end1813/1)
```c++
class Solution{
    public:
    void segregateElements(int arr[],int n)
    {
        vector<int>pos, neg, final;
        
        for(int i = 0; i < n; i++){
            if(arr[i] >= 0) pos.push_back(arr[i]);
            else neg.push_back(arr[i]);
        }
        
        //int ip = pos.size(), in = neg.size();
        
        for(int i = 0; i < n; i++){
            if(i < pos.size()) arr[i] = pos[i];
            else arr[i] = neg[i - pos.size()];
        }
    }
};
```

# [Arranging the array](https://practice.geeksforgeeks.org/problems/arranging-the-array1131/1)
```c++
class Solution
{
    public:
        void Rearrange(int arr[], int n)
        {
            vector<int>pos, neg;
            
            for(int i = 0; i < n; i++){
                if(arr[i] >= 0) pos.push_back(arr[i]);
                else neg.push_back(arr[i]);
            }
            
            for(int i = 0; i < n; i++){
                if(i < neg.size()) arr[i] = neg[i];
                else arr[i] = pos[i - neg.size()];
            }
        }
};
```

# [Positive and negative elements](https://practice.geeksforgeeks.org/problems/positive-and-negative-elements4613/1)
```c++
class Solution{
  public:
    vector<int> arranged(int a[],int n)
    {
        vector<int>pos, neg, res;
        int ip = 1, in = 0;
        
        for(int i = 0; i < n; i++){
            if(a[i] >= 0) pos.push_back(a[i]);
            else neg.push_back(a[i]);
        }
        
        for(int i = 0; i < n/2; i++){
            res.push_back(pos[i]);
            res.push_back(neg[i]);
        }
        
        return res;
    }
};
```

# [Rearrange array such that even positioned are greater than odd](https://practice.geeksforgeeks.org/problems/rearrange-array-such-that-even-positioned-are-greater-than-odd4804/1)
```c++
class Solution{
    public:
        vector<int> assign(int a[], int n)
    {
        vector<int>res;
        int l = 0, r = n-1;
        
        res.push_back(a[0]);
        
        for(int i = 1; i < n; i++){
            if(i % 2 && a[i] < a[i-1]) swap(a[i], a[i-1]);
            else if(i % 2 == 0 && a[i] > a[i-1]) swap(a[i],a[i-1]);
            
            res.push_back(a[i]);
        }
        
        return res;
    }
};
```

# [Sort in specific order](https://practice.geeksforgeeks.org/problems/sort-in-specific-order2422/1)
```c++
class Solution
{
  public:
    void sortIt(long long arr[], long long n)
    {
        vector<long long>odds, even;
        int idx = 0;
         
        for(int i = 0; i < n; i++){
            if(arr[i] % 2) odds.push_back(arr[i]);
            else even.push_back(arr[i]);
        }
         
        sort(odds.rbegin(), odds.rend());
        sort(even.begin(), even.end());
         
        for(auto &a : odds){
            arr[idx] = a;
            idx++;
        }
        
        for(auto &a : even){
            arr[idx] = a;
            idx++;
        }
    }
};
```

# [Move all zeroes to end of array](https://practice.geeksforgeeks.org/problems/move-all-zeroes-to-end-of-array0751/1)
```c++
class Solution{
public:
	void pushZerosToEnd(int arr[], int n) {
	    int j = 0;
	    
	    for(int i = 1; i < n; i++){
	        if(arr[j] != 0) j++;
	        else{
	            while(arr[i] == 0 && i < n)i++;
	            
	            if(i == n) break;
	            else{
	                arr[j] = arr[i];
	                arr[i] = 0;
	                i--;
	            }
	        }
	    }
	}
};
```

# [Rearrange an array with O(1) extra space](https://practice.geeksforgeeks.org/problems/rearrange-an-array-with-o1-extra-space3142/1)
```c++    
class Solution{
    public:
    // arr: input array
    // n: size of array
    //Function to rearrange an array so that arr[i] becomes arr[arr[i]]
    //with O(1) extra space.
    void arrange(long long arr[], int n) {
        for(int i=0;i<n;i++){
            arr[i]+=(arr[arr[i]]%n)*n;
        }
        for(int i=0;i<n;i++){
            arr[i]/=n;
        }
        
    }
};
```

# [Rearrange array alternately](https://practice.geeksforgeeks.org/problems/-rearrange-array-alternately-1587115620/1)
```c++
class Solution {
public:
    void rearrange(long long *arr, int n) {
        int low = 0, high = n - 1;
        long long max_element = arr[n - 1] + 1;
        for (int i = 0; i < n; i++) {
            if (i % 2 == 0) {
                arr[i] += (arr[high--] % max_element) * max_element;
            } else {
                arr[i] += (arr[low++] % max_element) * max_element;
            }
        }
        for (int i = 0; i < n; i++) {
            arr[i] /= max_element;
        }
    }
};
```

# [Rearrange array](https://practice.geeksforgeeks.org/problems/rearrange-the-array5802/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
class Solution{
  public:
    void rearrangeArray(int arr[], int n) {
        vector<int>aux;
        int l = 0, r = n-1, i = 0;
        
        sort(arr, arr+n);
        
        while(l <= r){
            aux.push_back(arr[l]);
            aux.push_back(arr[r]);
            r--;
            l++;
        }
        
        //if(i % 2 == 0) aux.push_back(arr[n/2])
        
        for(int i = 0; i < n; i++) arr[i] = aux[i];

    }
};
```

# [Radix sort](https://practice.geeksforgeeks.org/problems/radix-sort/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
int getMax(int arr[], int n)
{
    int mx = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > mx)
            mx = arr[i];
    return mx;
}
 
// A function to do counting sort of arr[]
// according to the digit
// represented by exp.
void countSort(int arr[], int n, int exp)
{
 
    // Output array
    int output[n];
    int i, count[10] = { 0 };
 
    // Store count of occurrences
    // in count[]
    for (i = 0; i < n; i++)
        count[(arr[i] / exp) % 10]++;
 
    // Change count[i] so that count[i]
    // now contains actual position
    // of this digit in output[]
    for (i = 1; i < 10; i++)
        count[i] += count[i - 1];
 
    // Build the output array
    for (i = n - 1; i >= 0; i--) {
        output[count[(arr[i] / exp) % 10] - 1] = arr[i];
        count[(arr[i] / exp) % 10]--;
    }
 
    // Copy the output array to arr[],
    // so that arr[] now contains sorted
    // numbers according to current digit
    for (i = 0; i < n; i++)
        arr[i] = output[i];
}
 
// The main function to that sorts arr[]
// of size n using Radix Sort
void radixsort(int arr[], int n)
{
 
    // Find the maximum number to
    // know number of digits
    int m = getMax(arr, n);
 
    // Do counting sort for every digit.
    // Note that instead of passing digit
    // number, exp is passed. exp is 10^i
    // where i is current digit number
    for (int exp = 1; m / exp > 0; exp *= 10)
        countSort(arr, n, exp);
}
```

# [Sort by absolute difference](https://practice.geeksforgeeks.org/problems/sort-by-absolute-difference-1587115621/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
class Solution{
    public:
    
    void sortABS(int arr[],int n, int k)
    {
        stable_sort(arr, arr+n, [&k](const auto &l, const auto &r){
        return abs(l - k) < abs(r - k);
        });
    }
};
```

# [Sort first half in ascending and second half in descending](https://practice.geeksforgeeks.org/problems/sort-first-half-in-ascending-and-second-half-in-descending1714/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
class Solution{
  public:
    void customSort(int arr[], int n) {
        vector<int>aux;
        
        sort(arr,arr + n/2);
        
        for(int i = (n/2); i < n; i++) aux.push_back(arr[i]);
        
        sort(aux.rbegin(), aux.rend());
        
        int idx = (n/2);
        
        for(auto &a : aux){
            arr[idx] = a;
            idx++;
        }
    }
};
```

Another solution 
```c++
class Solution{
  public:
    void customSort(int arr[], int n) {
        // code here  
        int k = n/2;
        sort(arr,arr+k);
        sort(arr+k, arr + n, greater<int>()); 
    }
};
```c++

# [Minimum Swaps to Sort](https://practice.geeksforgeeks.org/problems/minimum-swaps/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
class Solution 
{
    public:
    //Function to find the minimum number of swaps required to sort the array. 
	int minSwaps(vector<int>&nums)
	{
	    vector<pair<int,int>>idx;
	    int cont = 0;
	    
	    for(int i = 0; i < nums.size(); i++) idx.push_back({nums[i], i});
	    
	    sort(idx.begin(), idx.end());
	    
	    for(int i = 0; i < nums.size(); i++){
	        if(i != idx[i].second){
	            cont++;
	            swap(idx[i], idx[idx[i].second]);
	            i--;
	        }
	    }
	    
	    return cont;
	}
};
```

# [Bitonic Generator Sort](https://practice.geeksforgeeks.org/problems/bitonic-generator-sort3343/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)
```c++
class Solution{
	
	
	public:
	  
	void bitonicGenerator(int arr[], int n)
	{
		vector<int>odds, even;
		
		for(int i = 0; i < n; i++){
		    if(i % 2) odds.push_back(arr[i]);
		    else even.push_back(arr[i]);
		}
		
		sort(odds.rbegin(), odds.rend());
		sort(even.begin(), even.end());
		
		int i = 0;
		
		for(int x : even){
		    arr[i] = x;
		    i++;
		}
		
		for(int x : odds){
		    arr[i] = x;
		    i++;
		}
	}
		 

};
```
