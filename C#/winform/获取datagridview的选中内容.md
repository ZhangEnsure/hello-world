# 如何获取DataGridView中选中行的特定标题下的内容
> 21:15 2020/5/31
---
于我而言，我一般把这个用在datagridview中的**CellContentClick**的事件中。需要做的操作如下：
1. 声明一个DataGridViewRow的对象row。
2. 为row对象赋值并取得所要的结果。
```C#
//增加一个判定
if(datagridview.CurrentRow.Index > 0)//下标从0开始，证明选中某一行
{
    DataGridViewRow row = datagridview.CurrentRow;
    string text = row.Cells[1].Value.ToString();//获取所选行的第二列的内容
}

```
