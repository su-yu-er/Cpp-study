## 类模板与函数模板的区别

```c++

#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

//类模板与函数模板的区别
using namespace std;

//模板参数列表：<······>
template<class NameType, class AgeType = int>
class Person
{
public:
	Person(NameType name, AgeType age)
	{
		this->m_age = age;
		this->m_name = name;
	}

public:
	void print()
	{
		cout << this->m_name << ":" << this->m_age << endl;
	}

public:
	NameType m_name;
	AgeType m_age;
};

//类模板无自动类型推到
void test01()
{
	//错误：自动类型推导失败
	//Person p1("ccy", 21);

	Person<string, int>p2("jdfis", 32);
	p2.print();
}

//类模板无自动类型推导

int main()
{
	test01();
	return 0;
}
```

