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





## string赋值

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//stirng容器


//string赋值
void test02()
{
	//用等号赋值
	string str1;
	str1 = "hello world!!";

	//
	string str2;
	str2 = str1;

	string str3;
	str3 = 'a';
	cout << "str3:" << str3 << endl;

	string str4;
  //str.assign (字符串，赋值个数)
	str4.assign("hello world", 5);
	cout << "str4:" << str4 << endl;

	//等等
}



int main()
{
	//test01();
	test02();
	return 0;
}
```





## string查找、替换和拼接

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//stirng容器

//string 拼接
void test01() {

	string str1 = "H";
	str1 += "ello";
	cout << str1 << endl;

	str1 += ':';
	cout << str1 << endl;

	string str2 = "world!!";
	str1 += str2;
	cout << str1 << endl;

	str1.append(" good day");
	cout << str1 << endl;

	//截取前n个字符
	str1.append("!??!", 2);
	cout << str1 << endl;

	str1.append("abc cba", 4, 6);
	cout << str1 << endl;
}

//string 查找和替换
void test02() {
	//查找
	//查找成功：返回下标
	//查找失败：返回 -1
	string s1 = "abcdefgde";

	int t=s1.find("de");
	cout << t << endl;

	int tt = s1.rfind("de");
	cout << tt << endl;

	//替换
	string s2 = "abcdefg";
	s2.replace(0, 3, "1111");
	cout << s2 << endl;
 }


int main()
{
	//test01();
	test02();
	return 0;
}
```

