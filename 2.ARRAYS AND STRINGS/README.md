# ARRAYS AND STRINGS

## Program to find sum of matrices

```C++
#include <iostream>
using namespace std;
int main(){
	int ar[100][100],rows,cols,i,j;
	cout<<"enter number of rows:";
	cin>>rows;
	cout<<"enter number of cols:";
	cin>>cols;
	if(rows!=cols){
		cout<<"!!!!!please enter a square matrix only!!!!!";
		return 0;
	}
	else{
	cout<<"enter elements of"<<rows<<"*"<<cols<<"matrix: ";
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			cin>>ar[i][j];
		}
	}
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			cout<<ar[i][j]<<" ";
		}
		cout<<"\n";
	}
}
	int arr[100][100];
	cout<<"enter number of rows:";
	cin>>rows;
	cout<<"enter number of cols:";
	cin>>cols;
		if(rows!=cols){
		cout<<"!!!!!please enter a square matrix only!!!!!";
		return 0;
	}
	else{
	cout<<"enter elements of"<<rows<<"*"<<cols<<"matrix: ";
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			cin>>arr[i][j];
		}
	}
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			cout<<arr[i][j]<<" ";
		}
		cout<<"\n";
	}
}
	int a[100][100];
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			a[i][j]=ar[i][j]+arr[i][j];
			cout<<a[i][j]<<" ";
		}
		cout<<"\n";
	}
	int b[100][100];
	for(i=0;i<rows;i++){
		for(j=0;j<cols;j++){
			b[i][j]=ar[i][j]-arr[i][j];
			cout<<b[i][j]<<" ";
		}
		cout<<"\n";
	}
     return 0;
```

## Program to find min and max of a array

```C++
#include<iostream>
#include<cmath>
using namespace std;
int main()
{
    int arr[100],n;
    int m1 = 1000,m2 = -1000;
    cout<<"Enter the number of elements you want to enter: ";
    cin>>n;
    cout<<"Enter the elements: ";
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    for(int i=0;i<n;i++){
        m1 = min(m1,arr[i]);
    }
    for(int i=0;i<n;i++){
        m2 = max(m2,arr[i]);
    }
    cout<<"Minimum value in the array is: "<<m1<<endl;
    cout<<"Maximum value in the array is: "<<m2<<endl;
    return 0;
}
```