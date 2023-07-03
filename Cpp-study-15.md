## pair对

```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<set>
#include<algorithm>

using namespace std;

template<typename T>
void my_print(const T st)
{
	for (auto it = st.begin(); it != st.end(); ++it)
		cout << *it << " ";
	cout << endl;
}

void test01()
{
	pair<string,int>pr("cy",18);
	cout << pr.first << " " << pr.second << endl;

	pair<string, int>pr1 = make_pair("fsd", 333);
	cout << pr1.first << " " << pr1.second << endl;

}

//烫烫烫 o((>ω< ))o
int main()
{
	test01();
	return 0;
}
```





## 仿函数指定set排序规则

```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<set>
#include<algorithm>

using namespace std;

class MyCmp
{
public:
	//仿函数
	bool operator()(int val1, int val2) const
	{
		return val1 > val2;
	}
};

template<typename T>
void my_print(const T st)
{
	for (auto it = st.begin(); it != st.end(); ++it)
		cout << *it << " ";
	cout << endl;
}


void test01()
{
	set<int>st = { 1,4,2,5,3 };
	my_print(st);

	set<int, MyCmp>st2;

	st2.insert(10);
	st2.insert(40);
	st2.insert(20);
	st2.insert(30);
	st2.insert(50);

	my_print(st2);

}

//烫烫烫 o((>ω< ))o
int main()
{
	test01();
	return 0;
}
```





```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<set>
#include<algorithm>

using namespace std;

//当set存放自定义数据类型时如何排序
//自定义数据都要指定排序规则
class Person
{
public:
	string m_name;
	int m_age = 0;

	Person(string name, int age)
	{
		m_name = name;
		m_age = age;
	}
};

class Compare
{
public:
	bool operator()(const Person& p1, const Person& p2) const
	{
		return p1.m_age > p2.m_age;
	}
};

void my_print(const set<Person,Compare>& st)
{
	for (auto it = st.begin(); it != st.end(); ++it)
		cout << (*it).m_name << " " << (*it).m_age << endl;
}


void test01()
{
	Person p1("刘备", 23);
	Person p2("关羽", 27);
	Person p3("张飞", 25);
	Person p4("赵云", 21);

	set<Person,Compare>st = { p1,p2,p3,p4 };

	my_print(st);
}

//烫烫烫 o((>ω< ))o
int main()
{
	test01();
	return 0;
}
```

