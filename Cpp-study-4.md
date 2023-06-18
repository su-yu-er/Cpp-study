## 类模板对象做函数参数

```c++
#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

using namespace std;

template<typename T1,typename T2 = int>
class person
{
public:
	person(T1 name, T2 age)
	{
		this->m_age = age;
		this->m_name = name;
	}

	void show_person()
	{
		cout << "name:" << this->m_name << "age:" << this->m_age << endl;
	}

public:
	T1 m_name;
	T2 m_age;
};

//指定传入的类型
void print_person(person<string, int>&p1)
{
	p1.show_person();
}

//参数模板化
template<typename T1,typename T2>
void print_person2(person<T1, T2>p2)
{
	p2.show_person();
}

//整个类模板化
template<typename T>
void print_person3(T p3)
{
	p3.show_person();
	//自动类型推理查看
	cout << typeid(T).name() << endl;
}

int main()
{
	person<string,int> p("cycy", 666);
	print_person3(p);
	return 0;
}
```

