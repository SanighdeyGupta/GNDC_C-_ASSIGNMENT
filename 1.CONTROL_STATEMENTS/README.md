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
* Thus 2's complement is 1's complement of the number and than adding '1' in that number.

```C++
#include <bits/stdc++.h>
using namespace std;
 
// Returns '0' for '1' and '1' for '0'
char flip(char c) {return (c == '0')? '1': '0';}
 
// Print 1's and 2's complement of binary number
// represented by "bin"
void printOneAndTwosComplement(string bin)
{
    int n = bin.length();
    int i;
 
    string ones, twos;
    ones = twos = "";
 
    //  for ones complement flip every bit
    for (i = 0; i < n; i++)
        ones += flip(bin[i]);
 
    //  for two's complement go from right to left in
    //  ones complement and if we get 1 make, we make
    //  them 0 and keep going left when we get first
    //  0, make that 1 and go out of loop
    twos = ones;
    for (i = n - 1; i >= 0; i--)
    {
        if (ones[i] == '1')
            twos[i] = '0';
        else
        {
            twos[i] = '1';
            break;
        }
    }
 
    // If No break : all are 1  as in 111  or  11111;
    // in such case, add extra 1 at beginning
    if (i == -1)
        twos = '1' + twos;
 
 
    cout << "1's complement: " << ones << endl;
    cout << "2's complement: " << twos << endl;
}
 
// Driver program
int main()
{
    string bin = "1100";
    printOneAndTwosComplement(bin);
    return 0;
}
```

## Program that reads the number of upper_case,lower_case,digits,spaces and other characters?

```C++
#include<iostream>
using namespace std;

int main()
{
    char arr[100];
    int i = 0;
    int c1 = 0,c2 = 0,c3 = 0,c4 = 0,c5 = 0;
    cout<<"Enter the character line: ";
    cin>>arr;
    while(arr[i]!='\0'){
        if((arr[i]>=65) && (arr[i]<=90)){
            c1++;
        }
        else if((arr[i]>=97) && (arr[i]<=122)){
            c2++;
        }
        else if((arr[i]>=48) && (arr[i]<=57)){
            c3++;
        }
        else if(arr[i]==32){
            c4++;
        }
        else{
            c5++;
        }
        i++;
    }
    cout<<"Number of upper_case: "<<c1<<endl;
    cout<<"Number of lower_case: "<<c2<<endl;
    cout<<"Number of digits: "<<c3<<endl;
    cout<<"Number of spaces: "<<c4<<endl;
    cout<<"Number of other_char: "<<c5<<endl;
    return 0;
}
```