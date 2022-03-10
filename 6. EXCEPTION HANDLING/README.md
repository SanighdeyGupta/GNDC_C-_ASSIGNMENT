# EXCEPTION HANDLING

```C++
#include <iostream>

using namespace std;

int main(){
	int n;
	int *p;
	bool error=false;
    do{
        error=false;
	    cout<<"Input the number of elements: ";
        cin>>n;
    try{
	    p=new int[n];
    }
        catch(std::bad_alloc ex){
	    cout<<"New failed to allocate memory because: "<<ex.what()<<endl;
	    cout<<"Please input value for n again"<<endl;
	    error=true;
    }
}while(error);
	    cout<<"hello"<<endl;
	
	    delete [] p;
	    return 0;
}
```