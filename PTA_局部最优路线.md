# 浙大版《数据结构（第2版）》题目集
## 习题8.5 畅通工程之局部最小花费问题
某地区经过对城镇交通状况的调查，得到现有城镇间快速道路的统计数据，并提出“畅通工程”的目标：使整个地区任何两个城镇间都可以实现快速交通（但不一定有直接的快速道路相连，只要互相间接通过快速路可达即可）。现得到城镇道路统计表，表中列出了任意两城镇间修建快速路的费用，以及该道路是否已经修通的状态。现请你编写程序，计算出全地区畅通需要的最低成本。

输入格式:
输入的第一行给出村庄数目N (1≤N≤100)；随后的N(N−1)/2行对应村庄间道路的成本及修建状态：每行给出4个正整数，分别是两个村庄的编号（从1编号到N），此两村庄间道路的成本，以及修建状态 — 1表示已建，0表示未建。

输出格式:
输出全省畅通需要的最低成本。

输入样例:
4
1 2 1 1
1 3 4 0
1 4 1 1
2 3 3 0
2 4 2 1
3 4 5 0
输出样例:
3

作者
DS课程组
单位
浙江大学
代码长度限制
16 KB
时间限制
400 ms
内存限制

---
1. Understand the question
聚焦于**“局部”**二字，在开始调用Kruskal之前就应该计算已经修通的路程,不要重复计算。
2. Devise a plan
**高效的**并查集 + Kruskal。
3. Carry out
定义一个结构，并在结构的内部重载运算符。
4. Look back
重载运算符注意有无等于号的存在。

```
#include<iostream>
#include<algorithm>
#include<functional>
#include<vector>

using namespace std;
typedef struct load
{
	//其实没有什么顺序......
	int from;
	int to;
	int cost;
	bool operator<(const load& a)const
	{
		return cost < a.cost;
	}
}Load;//定义为Edge更佳！

vector<struct load> Load1;
vector<int> pre;//记录并查集的数组
//并查集的三个操作：初始化、查询、合并

void Init(int num)//num是指村庄的数量
{
	pre.resize(num + 1);
	for (int i = 0; i <= num; ++i)
	{
		pre[i] = i;
	}
}

int Find(int country_id)
{
	if (pre[country_id] != country_id) //证明不是孤独村庄，至少有一相连
	{
		pre[country_id] = Find(pre[country_id]);
	}
	return pre[country_id];//最后别返回错了！
}

//必定是判断两者不是相连的之后执行此操作
void Union(int country_id1, int country_id2)
{
	pre[Find(country_id1)] = pre[Find(country_id2)];
}

int Kruskal()
{
	int Load1Size = Load1.size(); 
	int sum = 0;
	sort(Load1.begin(), Load1.end());
	for (int i = 0; i < Load1Size; ++i)
	{
		if (Find(Load1[i].from) != Find(Load1[i].to))
		{
			sum += Load1[i].cost;
			Union(Load1[i].from, Load1[i].to);
		}
	}
	return sum;
}

int main()
{
	int countrynum, roadnum;
	cin >> countrynum;
	roadnum = (countrynum * (countrynum - 1)) / 2;
	Init(countrynum);
	for (int i = 0; i < roadnum; ++i)
	{
		int from, to, cost, status;
		cin >> from >> to >> cost >> status;
		if (status == 1)//路已经修好了
		{
			Union(from, to);
		}
		else
		{
			Load1.push_back({ from,to,cost});
		}
	}
	cout << Kruskal();
    return 0;
}

```





