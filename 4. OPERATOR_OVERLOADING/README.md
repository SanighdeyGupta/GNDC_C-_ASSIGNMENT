# OPERATOR OVERLOADING

```C++
#include<iostream>
using namespace std;

class circle{
    private:
        int radius;
        float area;
    public:
        circle(){}
        circle(int radius){
            this->radius = radius;
        }
        void calculate_area(){
            area = 3.14*(radius*radius);
        }
        void display(){
            cout<<"Area of the circle is: "<<area<<endl;
        }
        circle operator+(circle c1){
            circle c;
            c.radius = this->radius + c1.radius;
            return c;
        }
        circle operator++(){
            circle c;
            c.radius = this->radius + 1;
            return c;
        }
};

int main()
{
    circle c1(5),c2(10);
    c1.calculate_area();
    c1.display();
    circle c3;
    c3 = c1 + c2;
    c3.calculate_area();
    c3.display();
    c2 = ++c2;
    c2.calculate_area();
    c2.display();
    return 0;
}
```