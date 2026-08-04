# Top 20 C++ Coding Interview Questions and Answers

## 📌 Description

This repository contains the **Top 20 most frequently asked C++ coding interview questions** with optimized solutions and explanations. It is designed for beginners, college students, and software engineering interview preparation.

---

# 1. Reverse a String

### Problem

Reverse a given string.

### Solution

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    string s;
    cin >> s;
    reverse(s.begin(), s.end());
    cout << s;
}
```

**Time Complexity:** O(n)

---

# 2. Palindrome Number

### Problem

Check whether a number is palindrome.

### Solution

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, rev = 0, temp;
    cin >> n;
    temp = n;

    while (temp) {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }

    if (rev == n)
        cout << "Palindrome";
    else
        cout << "Not Palindrome";
}
```

**Time Complexity:** O(log n)

---

# 3. Fibonacci Series

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    int a = 0, b = 1;

    for (int i = 0; i < n; i++) {
        cout << a << " ";
        int c = a + b;
        a = b;
        b = c;
    }
}
```

**Time Complexity:** O(n)

---

# 4. Factorial of a Number

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    long long fact = 1;

    for (int i = 1; i <= n; i++)
        fact *= i;

    cout << fact;
}
```

---

# 5. Prime Number Check

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    bool prime = true;

    if (n <= 1)
        prime = false;

    for (int i = 2; i * i <= n; i++)
        if (n % i == 0)
            prime = false;

    if (prime)
        cout << "Prime";
    else
        cout << "Not Prime";
}
```

---

# 6. Find Largest Element in Array

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    int arr[n];

    for (int i = 0; i < n; i++)
        cin >> arr[i];

    int mx = arr[0];

    for (int i = 1; i < n; i++)
        mx = max(mx, arr[i]);

    cout << mx;
}
```

---

# 7. Second Largest Element

```cpp
#include <iostream>
#include <climits>
using namespace std;

int main() {
    int n;
    cin >> n;

    int arr[n];
    for(int i=0;i<n;i++)
        cin>>arr[i];

    int first=INT_MIN, second=INT_MIN;

    for(int i=0;i<n;i++){
        if(arr[i]>first){
            second=first;
            first=arr[i];
        }
        else if(arr[i]>second && arr[i]!=first)
            second=arr[i];
    }

    cout<<second;
}
```

---

# 8. Reverse an Array

```cpp
#include<iostream>
using namespace std;

int main(){
    int n;
    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    for(int i=n-1;i>=0;i--)
        cout<<arr[i]<<" ";
}
```

---

# 9. Count Digits

```cpp
#include<iostream>
using namespace std;

int main(){
    int n,count=0;
    cin>>n;

    while(n){
        count++;
        n/=10;
    }

    cout<<count;
}
```

---

# 10. Armstrong Number

```cpp
#include<iostream>
#include<cmath>
using namespace std;

int main(){

    int n,temp,sum=0;
    cin>>n;

    temp=n;

    while(temp){
        int d=temp%10;
        sum+=pow(d,3);
        temp/=10;
    }

    if(sum==n)
        cout<<"Armstrong";
    else
        cout<<"Not Armstrong";
}
```

---

# 11. Bubble Sort

```cpp
#include<iostream>
using namespace std;

int main(){

    int n;
    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)
            if(arr[j]>arr[j+1])
                swap(arr[j],arr[j+1]);

    for(int x:arr)
        cout<<x<<" ";
}
```

---

# 12. Binary Search

```cpp
#include<iostream>
using namespace std;

int main(){

    int n,target;
    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    cin>>target;

    int l=0,r=n-1;

    while(l<=r){

        int mid=(l+r)/2;

        if(arr[mid]==target){
            cout<<"Found";
            return 0;
        }

        if(arr[mid]<target)
            l=mid+1;
        else
            r=mid-1;
    }

    cout<<"Not Found";
}
```

---

# 13. Linear Search

```cpp
#include<iostream>
using namespace std;

int main(){

    int n,key;
    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    cin>>key;

    for(int i=0;i<n;i++)
        if(arr[i]==key){
            cout<<i;
            return 0;
        }

    cout<<-1;
}
```

---

# 14. GCD of Two Numbers

```cpp
#include<iostream>
using namespace std;

int main(){

    int a,b;
    cin>>a>>b;

    while(b){
        int t=b;
        b=a%b;
        a=t;
    }

    cout<<a;
}
```

---

# 15. LCM of Two Numbers

```cpp
#include<iostream>
using namespace std;

int gcd(int a,int b){
    while(b){
        int t=b;
        b=a%b;
        a=t;
    }
    return a;
}

int main(){

    int a,b;
    cin>>a>>b;

    cout<<(a*b)/gcd(a,b);
}
```

---

# 16. Remove Duplicates from Sorted Array

```cpp
#include<iostream>
using namespace std;

int main(){

    int n;
    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    int j=0;

    for(int i=1;i<n;i++)
        if(arr[i]!=arr[j])
            arr[++j]=arr[i];

    for(int i=0;i<=j;i++)
        cout<<arr[i]<<" ";
}
```

---

# 17. Check Anagram

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

int main(){

    string a,b;

    cin>>a>>b;

    sort(a.begin(),a.end());
    sort(b.begin(),b.end());

    if(a==b)
        cout<<"Anagram";
    else
        cout<<"Not Anagram";
}
```

---

# 18. Merge Two Sorted Arrays

```cpp
#include<iostream>
#include<vector>
using namespace std;

int main(){

    int n,m;

    cin>>n>>m;

    vector<int>a(n),b(m);

    for(int &x:a) cin>>x;
    for(int &x:b) cin>>x;

    int i=0,j=0;

    while(i<n && j<m){
        if(a[i]<b[j])
            cout<<a[i++]<<" ";
        else
            cout<<b[j++]<<" ";
    }

    while(i<n) cout<<a[i++]<<" ";
    while(j<m) cout<<b[j++]<<" ";
}
```

---

# 19. Two Sum

```cpp
#include<iostream>
#include<unordered_map>
using namespace std;

int main(){

    int n,target;

    cin>>n;

    int arr[n];

    for(int i=0;i<n;i++)
        cin>>arr[i];

    cin>>target;

    unordered_map<int,int> mp;

    for(int i=0;i<n;i++){

        int x=target-arr[i];

        if(mp.count(x)){
            cout<<mp[x]<<" "<<i;
            return 0;
        }

        mp[arr[i]]=i;
    }
}
```

---

# 20. Valid Parentheses

```cpp
#include<iostream>
#include<stack>
using namespace std;

int main(){

    string s;
    cin>>s;

    stack<char> st;

    for(char c:s){

        if(c=='('||c=='{'||c=='[')
            st.push(c);

        else{

            if(st.empty()){
                cout<<"Invalid";
                return 0;
            }

            if((c==')'&&st.top()=='(')||
               (c=='}'&&st.top()=='{')||
               (c==']'&&st.top()=='['))
                st.pop();
            else{
                cout<<"Invalid";
                return 0;
            }
        }
    }

    if(st.empty())
        cout<<"Valid";
    else
        cout<<"Invalid";
}
```

---

# 🎯 Topics Covered

* Arrays
* Strings
* Searching
* Sorting
* Recursion
* Mathematics
* Hashing
* STL
* Stack
* Number Theory

---

# 💻 Requirements

* C++11 or above
* GCC / G++
* Visual Studio Code
* Code::Blocks
* CLion

---

# ⭐ Contribute

Contributions are welcome! Feel free to fork this repository, improve solutions, optimize algorithms, or add more interview questions.

---

## 📄 License

This project is open-source and available under the MIT License.

---

### ⭐ If this repository helped you, don't forget to Star it on GitHub!
