## vector容器

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

void printVector(vector<int> &v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); ++it)
	{
		cout << *it << " ";
	}
	cout << endl;
}

//vector容器
// 
//构造方法
void test01() {
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	printVector(v1);

	vector<int>v2(v1.begin(), v1.end());
	printVector(v2);

	vector<int>v3(10, 6);
	printVector(v3);

	vector<int>v4(v3);
	printVector(v4);
}

//赋值
void test02() {
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}

	vector<int>v2;
	v2 = v1;

	vector<int>v3;
	v3.assign(10, 6);	//十个六
	v3.assign(v1.begin(), v2.end());
}

int main()
{
	test01();
	//test02();
	return 0;
}
```

