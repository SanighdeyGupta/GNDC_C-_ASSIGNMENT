# TEMPLATES

```C++
#include<iostream>
#include<list>
#include<vector>
#include<cstdlib>
#include<ctime>

using namespace std;

bool iseven(int val){
    return val%2 == 0;
}

bool isodd(int val){
    return val%2 != 0;
}

template <class iterator>
int count_function(iterator start, iterator end, auto criteria){
    int count = 0;
    for(; start !=end; ++start){
        if(criteria(*start)){
            count++;
        }
    }
    return count;
}

int main()
{
    vector<int> v {1,2,3,4,5,6,7,8,9,10,11,12,13};
    int count1 = count_function(v.begin(), v.end(), isodd);
    cout<<"count1: "<<count1<<endl;
    int count2 = count_function(v.begin(),v.end(),iseven);
    cout<<"count2: "<<count2<<endl;
    return 0;
```

# FILE HANDLING

```C++
#include <iostream>
#include <fstream>
using namespace std;
int main()
{
    ofstream fout;
    string line;
    fout.open("sample.txt");
    while (fout) {
        getline(cin, line);
        if (line == "-1")
            break;
        fout << line << endl;
    }
    fout.close();
    ifstream fin;
    fin.open("sample.txt");
    while (fin) {
        getline(fin, line);
        cout << line << endl;
    }
    fin.close();
    return 0;
}
```