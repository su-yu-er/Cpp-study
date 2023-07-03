## 队列

```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<algorithm>

using namespace std;

class Person
{
public:
	Person(string name, int age)
	{
		m_name = name;
		m_age = age;
	}

	string m_name;
	int m_age = 18;
};

int main()
{
	queue<Person>que;
	
	Person p1("张三", 22);
	Person p2("李四", 25);
	Person p3("黄无", 21);
	Person p4("小七", 29);

	que.push(p1);
	que.push(p2);
	que.push(p3);
	que.push(p4);

	if (que.empty())
		cout << "队空" << endl;
	else
		cout << "队不为空" << endl;

	while (!que.empty())
	{
		cout << "队头元素: " << que.front().m_name << ": " << que.front().m_age << endl;
		cout << "队尾元素: " << que.back().m_name << ": " << que.back().m_age << endl;
		que.pop();
	}
	cout << "队列大小：" << que.size() << endl;

	return 0;
}
```

