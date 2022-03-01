# CONTROL STATEMENTS

## Program to find the area and circumfrence of the circle?

```C++
#include<iostream>
#include<cmath>
using namespace std;

#define p 3.14

int main()
{
    int rad = 0;
    float area;
    float circumfrence;
    cout<<"Enter the value of the radius: ";
    cin>>rad;
    area = p*(pow(rad,2));
    circumfrence = (2*p)*rad;
    cout<<"Area of the circle is "<<area<<endl;
    cout<<"Circumfrence of the circle is "<<circumfrence<<endl;
    return 0;
}
```

## Program to swap the value of two numbers?

```C++
#include<iostream>
using namespace std;
int main()
{
    int a,b;
    cout<<"Enter the value of the two numbers: ";
    cin>>a>>b;
    cout<<"Numbers before swapping = "<<a<<" "<<b<<endl;
    a = a+b;
    b = a-b;
    a = a-b;
    cout<<"Numbers after swapping = ";
    cout<<a<<" "<<b<<endl;
    return 0;
}
```

## Program to find the roots of a quadratic equation?

```C++
#include<iostream>
#include<cmath>
using namespace std;
int main()
{
    //quadratic equation ax^2 + bx +c
    int a,b,c;
    float D;
    float x1,x2;
    cout<<"Enter the value of a,b and c: ";
    cin>>a>>b>>c;
    cout<<"The given quadratic equation is: "<<a<<"x^2 + "<<b<<"x + "<<c<<endl;
    D = (pow(b,2)) - (4*a*c);
    x1 = (-b + (sqrt(D)))/(2*a);
    x2 = (-b - (sqrt(D)))/(2*a);
    cout<<"Roots of the given quadratic equation are: "<<x1<<" and "<<x2<<endl;
    return 0;
}
```

## Find the 2's complement of a binary number?

* 2's complement of a number is obtained by scanning it from right to left and complementing all the bits after the appearance of a 1.
* Thus 2's complement of 111000(56) is 00100(8).

```C++
#include<iostream>
using namespace std;
int main()
{
    int num = 0,i = 0,arr[100],temp;
    cout<<"Enter the binary number: ";
    cin>>num;
    while(num!=0){
        arr[i] = num%10;
        num = num/10;
        i++;
    }
    i = i-1;
    temp = i;
    for(i=0;i<=temp;i++){
        if(arr[i]==1){
            i++;
            while(i<=temp){
                arr[i]=0;
                i++;
            }  
            break;
        }
    } 
    for(i=temp;i>=0;i--){
        cout<<arr[i];
    }
    cout<<endl; 
    return 0;
}
```