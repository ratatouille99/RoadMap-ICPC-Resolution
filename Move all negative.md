### Move all negative numbers to beginning and positive to end with constant extra space

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
