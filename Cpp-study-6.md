## 类模板和友元

```c++

#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

//类模板和友元
using namespace std;

template<class T1, class T2>
class Person;

template<typename T1, typename T2>
void show1_person(Person<T1, T2>p)
{

}

template<class T1,class T2>
class Person
{
	////全局函数
	//friend void show_person(Person<T1, T2>p)
	//{
	//	cout << "naem: " << p.m_name << endl;
	//	cout << "age: " << p.m_age << endl;
	//}

	//
	friend void show1_person<>(Person<T1, T2>p);

public:
	Person(T1 name, T2 age)
	{
		m_name = name;
		m_age = age;
	}


private:
	T1 m_name;
	T2 m_age;
};


//void text01()
//{
//	Person<string, int>p("tom", 22);
//	show_person(p);
//}

void text02()
{
	Person<string, int>p("tom", 12);
	show1_person(p);
}

int main()
{
	text02();
	return 0;
}
```

