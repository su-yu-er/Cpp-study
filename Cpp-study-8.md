##  vector存放内置数据类型

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>

using namespace std;

//vector容器存放数据类型

void print(int val)
{
	cout << val << endl;
}

int main()
{
	vector<int>v;

	//尾插数据
	v.push_back(10);
	v.push_back(20);
	v.push_back(30);
	v.push_back(40);

	/*vector<int>::iterator itBegin = v.begin();
	vector<int>::iterator itEnd = v.end();

	while (itBegin != itEnd)
	{
		cout << *itBegin << endl;
		itBegin++;
	}*/

	/*for (vector<int>::iterator it = v.begin(); it != v.end(); ++it)
	{
		cout << *it << endl;
	}*/

	for_each(v.begin(),v.end(),print);

	/*for_each()*/
	
	return 0;
}
```

