```C++
#include <iostream>
using namespace std ;
int main()
{
	int n, num = 1, maxr = 1;
	cin>>n;
	int *r = new int[n];//创建长为n的数组
	int *r1 = new int[n];//备用数组
	for (int i = 0; i < n; i++)
	{
		cin>>r[i];//写入数字
	}
	for (int i = 0; i < n; i++)
	{
		r1[i] = r[i];//从原数组中复制第i个数字,以防止原数组在计算过程中被改变
		for (int j = i+1; j < n; j++)
		{
			r1[j] = r[j];//从原数组中复制第j个数字
			if (r1[i]+1 == r1[j])//判断相邻两数字是否递增1
			{
				num = num + 1;//递增1子序列的长度	
				r1[i] = r1[j];
			}
		}
		if (num > maxr)//更新递增1子序列的长度
		{
			maxr = num;
		}
		num = 1;
	}
	cout<<n-maxr<<endl;
	system("PAUSE");
}
```