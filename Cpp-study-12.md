## 打分案例

```c++
#include<iostream>
#include<fstream>
#include<string>
#include<vector>
#include<algorithm>
#include<deque>
#include <cstdlib>
#include <ctime>

using namespace std;

int n = 3;
int m = 10;

class Player
{
public:
	Player(string name, int score = 0)
	{
		m_name = name;
		m_score = score;
	}

public:
	string m_name;
	double m_score = 0;
};


void printPlayer(const vector<Player>& v)
{
	for (vector<Player>::const_iterator it = v.begin(); it != v.end(); ++it)
	{
		cout << "姓名：" << (*it).m_name << "  " << "\t分数：" << (*it).m_score << endl;
	}
}

void setScore(Player& p)
{
	deque<int>d;
	srand(time(nullptr));
	for (int i = 0; i < m; ++i)
	{
		int score = rand() % 41 + 60;
		d.push_back(score);
	}
	sort(d.begin(), d.end());
	d.pop_front();
	d.pop_back();
	for (int i = 0; i < m - 2; ++i)
	{
		cout << d.at(i) << " ";
	}
	int sum = 0;
	for (deque<int>::iterator it = d.begin(); it != d.end(); ++it)
	{
		sum += *it;
	}

	p.m_score = (double)(sum / (m - 2));
}

//double Averaging(deque<int>& d)
//{
//
//}

void createPlayer(vector<Player>& v)
{
	string name;
	string player = "ABCDEF";
	int score = 0;
	for (int i = 0; i < n; ++i)
	{
		cout << "输入选手" << player.at(i) << "姓名：";
		cin >> name;
		cout << "生成选手" << player.at(i) << "分数";
		Player p(name);
		setScore(p);
		cout << endl;

		v.push_back(p);
	}
}

int main()
{
	vector<Player>v;
	createPlayer(v);
	printPlayer(v);

	return 0;
}
```

