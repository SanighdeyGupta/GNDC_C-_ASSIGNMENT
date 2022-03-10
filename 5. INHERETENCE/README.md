# INHERITENCE

```C++
#include <iostream>
#include <cstring>
using namespace std;

class employee{
	protected:
		string name;
		int age;
		double basic;
	public:
		employee(string name,int age ,double basic){
		this->name=name;
		this->age=age;
		this->basic=basic;
		}
        virtual double calculatesalary(){
        double salary=basic+basic*0.1;
        return salary;
		}	
};

class manager:public employee{
	private:
		double hra;
	public:
		manager(string name,int age,double basic):employee(name,age,basic){
		
		}
    double calculatesalary(){
	double salary=employee::calculatesalary();
	hra=basic*0.15;
	salary=salary+hra;
	return salary;
        }
}; 


class factoryworker:public employee{
	private:
		double tiffinallowences;
	public:
		factoryworker(string name,int age, double basic):employee(name,age,basic){
		tiffinallowences=0.05*basic;
		}
		double calculatesalary(){
		double salary=employee::calculatesalary();
		salary+=tiffinallowences;
		return salary;
		}
};

class clerk:public employee{
	private:
		int othours;
		double otrate;
	public:
		clerk(string name,int age,double basic,int othours,int otrate):employee(name,age,basic){
			this->othours=othours;
			this->otrate=otrate;
		}
		double calculatesalary(){
			double salary=employee::calculatesalary();
			salary+=otrate*othours;
			return salary;
		}
};

class club{
	public:
		string getmembershiptype(employee *p){
		double salary=p->calculatesalary();
		if(salary>=10000.00){
		return "RED";
		}
			else if(salary>=7500.00){
				return "BLUE";
			}
			else{
				return "GREY";
			}
		}
};

int main(){
//  employee *p=new manager("akice",25,8000.00);
//	double salary=p->calculatesalary();
//  cout <<salary;
    club club;
    cout<<"alice: "<<club.getmembershiptype(new manager("alice",25,8000.00))<<endl;
    cout<<"alien: "<<club.getmembershiptype(new clerk("alien",23,5000.00,10,12.5))<<endl;
	return 0;
```

