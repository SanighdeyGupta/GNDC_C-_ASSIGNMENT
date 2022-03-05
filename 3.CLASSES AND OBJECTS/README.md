# CLASSES AND OBJECTS

```C++
#include<iostream>
#include<cstring>
using namespace std;

class student;
void data(student &x);

class student{
    private:
        static int roll_no;
        string name;
        int marks;
        long long int contact;
        char* email;
    public:
        //default constructor
        student(){
            
        }
        //parameterized constructor
        student(string name){
            this->name = name;
        }
        //copy constructor
        student(student &x){
            this->roll_no = x.roll_no;
            this->name = x.name;
            this->marks = x.marks;
            this->contact = x.contact;
            //shallow copy
            strcpy(email,x.email);
        }
        void setdata(long long int contact,char* email,string name,int marks){
            this->name = name;
            this->marks = marks;
            this->contact = contact;
            //deep copy
            this->email = new char [strlen(email)+1];
            strcpy(this->email,email);
        }
        void getdata();
        ~student(){
            cout<<"Deleting "<<email<<endl;
            if(email!=NULL){
                delete [] email;
                email = NULL;
            }
        }
        friend void data(student &x);
};
inline void student::getdata(){
            cout<<"ROLL NUMBER  "<<"NAME  "<<"MARKS OBTAINED  "<<endl;
            cout<<roll_no<<"            "<<" "<<name<<"            "<<marks<<"        "<<endl;
            this->roll_no++;
        }
int student::roll_no = 1;

void data(student &x){
    cout<<"Contact number of student "<<x.name<<" is "<<x.contact<<endl;
    cout<<"Email of the student "<<x.name<<" is "<<x.email<<endl;
}

int main()
{
    student s1("Johnny");
    s1.setdata(9779746816,"gmail.com","Jack",88);
    s1.getdata();
    data(s1);
    return 0;
}
```