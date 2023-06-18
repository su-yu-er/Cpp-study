## //类模板语法

```c++
#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

//类模板语法
using namespace std;

template<class NameType,class AgeType>
class Person
{
public:
	Person(NameType name, AgeType age)
	{
		this->m_age = age;
		this->m_name = name;
	}

public:
	NameType m_name;
	AgeType m_age;
};

void test01()
{
	Person<string, int>p1("ccy", 21);
	cout << p1.m_name << ":" << p1.m_age << endl;
}

int main()
{
	test01();
	return 0;
}
```

