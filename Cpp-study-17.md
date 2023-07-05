## 仿函数



```c++
#include<iostream>
#include<fstream>

#include<vector>
#include<stack>
#include<deque>
#include<queue>
#include<list>
#include<set>
#include<map>
#include<functional>
#include<algorithm>

using namespace std;

template<typename T>
void my_print(T& mp)
{
	for (auto it = mp.begin(); it != mp.end(); ++it)
		cout << *it << " ";
	cout << endl;
}

class My_cmp
{
public:
	bool operator()(int val1, int val2) const
	{
		return val1 > val2;
	}
};

//void test01()
//{
//	//取反仿函数
//	negate<int>n;
//	cout << n(50) << endl;
//
//	//取模仿函数
//	modulus<int>m;
//	cout << m(3, 10) << endl;
//
//	//除法仿函数
//	divides<int>d;
//	cout << d(16, 8) << endl;
//
//	//减法仿函数
//	minus<int>mi;
//	cout << mi(10, 2) << endl;
//}

//void test02()
//{
//	vector<int>vct = { 4,2,6,3,7,9,8 };
//	sort(vct.begin(), vct.end(), less<int>());
//	my_print(vct);
//}

void test03()
{
	map<int, int, My_cmp>mp = { {1,10},{2,20},{3,30},{4,40},{5,50} };

	for (auto it = mp.begin(); it != mp.end(); ++it)
	{
		cout << "key= " << it->first << " value= " << it->second << endl;
	}
}

//烫烫烫 o((>ω< ))o Segment error
int main()
{
	//test01();
	//test02();
	test03();
	return 0;
}

```

