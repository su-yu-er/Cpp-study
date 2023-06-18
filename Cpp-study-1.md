## 模板的局限性和解决



```c++
#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

//模板的局限性
using namespace std;

class Person
{
public:
	string m_name;
	int m_age = 18;

public:
	Person(string name, int age)
	{
		m_age = age;
		m_name = name;
		cout << "有参构造" << endl;
	}
	

	//运算符“=”重载operator
	//解决模板局限性的方法之一
	bool operator==(Person& p)
	{
		if (this->m_age == p.m_age && this->m_name == p.m_name)
			return 1;
		else
			return 0;
	}

};

//模板具体化用template<>来开头
//具体化，显示具体化的原型和定意思以template<>开头，并通过名称来指出类型
template<>bool my_cmp(Person& p1, Person& p2)
{
	if (p1.m_age == p2.m_age && p1.m_name == p2.m_name)
		return 1;
	else
		return 0;
}

template<typename T>
bool my_cmp(T& a, T& b)
{
	if (a == b)
		return 1;
	else
		return 0;
}

void test02()
{
	Person p1("Tom", 10);
	Person p2("Tom", 11);

	if (my_cmp(p1, p2))
		cout << "p1==p2" << endl;
	else
		cout << "p1!=p2" << endl;

}

void test01()
{
	int a = 10, b = 11;
	if (my_cmp(a, b))
		cout << "a==b" << endl;
	else
		cout << "a!=b" << endl;
}

int main()
{
	//test01();
	test02();
	return 0;
}
```

