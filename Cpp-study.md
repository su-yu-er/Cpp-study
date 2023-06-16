```c++
#include<iostream>
#include<algorithm>
#include<string>
#include<fstream>

using namespace std;

void my_print(int a, int b)
{
	printf("调用的普通函数");
}

template<typename T>
void my_print(T a, T b)
{
	printf("调用的模板函数");
}

template<typename T>
void my_print(T a, T b, T c)
{
	printf("调用的重载模板函数");
}

void test01()
{
	int a = 10, b = 12;
	//my_print(a, b);

	//通过空模板强制调用模板函数
	//my_print<>(a, b,100);
	
	//如果模板函数可以产生更好的匹配，优先使用函数模板
	char a1 = 'a';
	char b1 = 'b';
	my_print(a1, b1);

}

int main()
{
	test01();
	return 0;
}
```

