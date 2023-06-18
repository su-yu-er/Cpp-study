## 1、类模板与继承

```c++
#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

using namespace std;

//类模板的继承
template<typename T>
class Base
{
public:
	T m_a;
};

template<typename T1, typename T2>
class Son :public Base<T1>
{
	T2 obj;
};

int main()
{
	Son<int, char>so;
	return 0;
}
```





## 2、 类模板成员函数类外实现

```c++

#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

using namespace std;

template<typename T1,typename T2>
class Person
{
public:
	/*Person(T1 name, T2 age)
	{
		this->m_age = age;
		this->m_naem = name;
	}*/
	Person(T1 naem, T2 age);
	void showPerson();

public:
	T1 m_naem;
	T2 m_age;
};

template<typename T1, typename T2>
Person<T1, T2>::Person(T1 naem, T2 age)
{
	this->m_age = age;
	this->m_naem = name;
}

void Person<string, int>::showPerson()
{
	cout << "naem:" << this->m_naem << "age:" << m_age << endl;
}

int main()
{
	Person<string, int>p("ccyy", 66);
	p.showPerson();

	return 0;
}
```

