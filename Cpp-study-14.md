## list的翻转和排序

```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<algorithm>

using namespace std;

void printList(const list<int>& lst)
{
	for (list<int>::const_iterator it = lst.begin(); it != lst.end(); ++it)
		cout << *it << " ";
	cout << endl;
}

void my_print(int val)
{
	cout << val << " ";
}

int my_cmp(int val1, int val2)
{
	return val1 > val2;
}


int main()
{
	list<int>lst = { 2,4,1,7,5,9,6,10 };

	printList(lst);

	cout << "翻转后：" << endl;
	lst.reverse();
	for_each(lst.begin(), lst.end(), my_print);
	cout << endl;

	lst.sort();
	printList(lst);

	lst.sort(my_cmp);
	printList(lst);

	return 0;
}

```





## list排序案例

```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<algorithm>

using namespace std;

class Person
{
public:
	string m_name;
	int m_age = 18;
	int m_height = 170;

	Person(string name, int age, int height)
	{
		this->m_age = age;
		this->m_height = height;
		this->m_name = name;
	}
};

void my_print(Person p)
{
	cout <<"姓名："<< p.m_name <<"  年龄："<< p.m_age << "  身高："<<p.m_height << endl;
}

int my_cmp(Person p1, Person p2)
{
	if (p1.m_age != p2.m_age)
		return p1.m_age < p2.m_age;
	else
		return p1.m_height > p2.m_height;
}

void test01()
{
	list<Person>lst_p;

	Person p1("刘备", 35, 175);
	Person p2("曹操", 45, 180);
	Person p3("孙权", 40, 170);
	Person p4("赵云", 25, 190);
	Person p5("张飞", 35, 160);
	Person p6("关羽", 35, 200);

	lst_p = { p1,p2,p3,p4,p5,p6 };
	for_each(lst_p.begin(), lst_p.end(), my_print);

	cout << "-------------------------------" << endl;
	lst_p.sort(my_cmp);
	for_each(lst_p.begin(), lst_p.end(), my_print);
}

int main()
{
	test01();
	return 0;
}
```

