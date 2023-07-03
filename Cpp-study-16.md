## map构造、赋值和交换

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
#include<algorithm>

using namespace std;

template<typename T>
void my_print(T& mp)
{
	for (auto it = mp.begin(); it != mp.end(); ++it)
		cout << "key=" << it->first << " " << "value=" << it->second << endl;
}

void test01()
{
	map<int, string>mp1;
	mp1 ={ {1, "a"}, { 2,"b" } };
	my_print(mp1);
	cout << "=================" << endl;

	map<int, string>mp2;
	mp2 = { {3,"c"},{4,"d"},{5,"e"} };
	my_print(mp2);
	cout << "=================" << endl;

	mp1.swap(mp2);
	my_print(mp1);
	my_print(mp2);

}

//烫烫烫 o((>ω< ))o Segment error
int main()
{
	test01();
	return 0;
}
```

