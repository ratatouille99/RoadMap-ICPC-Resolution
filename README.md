<h3 align="center">
    <img src="https://foundation.icpc.global/wp-content/uploads/2023/05/2023-icpc-foundation-logo-3c@300.png" width="100" alt="Logo"/><br/>
</h3>

# RoadMap-Resolution

## DESCRIPTION
The codes correspond to an Excel file that contains various exercises that serve as a guide for the preparation and improvement of skills on the topics addressed by competitive programming.  

The links to the exercises are inside the file and also in the header of the files that contain the code.

## LINK OF ROADMAP
[ROADMAP](https://docs.google.com/spreadsheets/d/1yrlqsx18S8H3f-kIQxv9x4GiY9nWaQ84/edit?usp=sharing&ouid=115071307096248007934&rtpof=true&sd=true)

## TYPICAL OUTPUTS/INPUTS ROUTINES

### - The number of test cases is given in the first line of the input.
```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    int t{};
    cin>>t;
    
    while(t--){
        int a{}, b{};
        cin>>a>>b;
        
        cout<<a<<' '<<b<<endl;
    }
    
    return 0;
}
```


### - The multiple test cases are terminated by special values (usually zeroes).
```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    int a{}, b{};
    
    while(cin>>a>>b, (a||b)){
        cout<<a<<' '<<b<<endl;
    }
    
    return 0;
}
```


### - The multiple test cases are terminated by the EOF (end-of-file) signal.
```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    int a{}, b{};
    
    while(cin>>a>>b, !cin.eof()){
        cout<<a<<' '<<b<<endl;
    }
    
    return 0;
}
```


