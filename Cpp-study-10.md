## 容器嵌套

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//容器嵌套

void test01()
{
	vector<vector<int>>v;
	
	vector<int>v1;
	vector<int>v2;
	vector<int>v3;

	for (int i = 0; i < 3; ++i)
	{
		v1.push_back(i + 1);
		v2.push_back(i + 2);
		v3.push_back(i + 3);
	}

	v.push_back(v1);
	v.push_back(v2);
	v.push_back(v3);

	for (vector<vector<int>>::iterator it = v.begin(); it != v.end(); ++it)
	{
		for (vector<int>::iterator vit = (*it).begin(); vit != (*it).end(); ++vit)
		{
			cout << (*vit) << " ";
		}
		cout << endl;
	}
}

int main()
{
	test01();
	return 0;
}
```





## string容器初始化

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//string容器初始化

void test01()
{
	string s1;	//默认构造

	//用c的字符串创建c++string
	const char* str = "hello world!!";
	string s2(str);
	cout << s2 << endl;

	//拷贝构造string
	string s3(s2);
	cout << "s3:" << s3 << endl;

	//n个字符初始化string
	string s4(10, 'c');
	cout << "s4:" << s4 << endl;
}

int main()
{
	test01();
	return 0;
}
```

