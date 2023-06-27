## vector容器存放数据类型

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//vector容器存放数据类型

class Person
{
public:
	Person(string name, int age)
	{
		m_name = name;
		m_age = age;
	}

public:
	string m_name;
	int m_age = 18;
};

void test01()
{
	vector<Person>v;
	Person p1("aaa", 10);
	Person p2("aba", 11);
	Person p3("abc", 12);
	Person p4("bcd", 13);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);

	for (vector<Person>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << (*it).m_name << endl;
		cout << it->m_age << endl;
	}
}

void test02()
{
	vector<Person*>v;
	Person p1("aaa", 10);
	Person p2("aba", 11);
	Person p3("abc", 12);
	Person p4("bcd", 13);

	v.push_back(&p1);
	v.push_back(&p2);
	v.push_back(&p3);
	v.push_back(&p4);

	for (vector<Person*>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << (**it).m_name<<": "
			 <<(**it).m_age << endl;
	}
}

void print(int val)
{
	cout << val << endl;
}

int main()
{
	vector<int>arr;
	arr.push_back(100);
	vector<int>::iterator Begin = arr.begin();
	test02();
	return 0;
}
```

