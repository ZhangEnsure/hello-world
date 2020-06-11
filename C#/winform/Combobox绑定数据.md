# ComboBox解决绑定数据出现System.Data.DataRowView问题
> 23:14 2020/5/31
---

## 文章背景
今天在写作业时遇见一个问题。在combobox绑定数据源时，一般需要设置两个属性：DisplayMember和ValueMember。前者是显示的值，后者是对应的值。
但我在实际的应用中发现、有时不一定要有显示的值和对应的值两者同时存在的呀！所以我只是选择了设置DisplayMember属性。但在获取SelectedValue时
一直显示的是System.Data.DataRowView。

### 解决方案：
1. 网上有人说是因为ValueMember没有设置的原因。我把DisplayMember和ValueMember均绑定DataTable的同一列时，还是报错。  
最后我尝试直接设置ValueMember而不设置DisplayMember，竟然成功了。自己尝试一下吧！
```C#
//组合框的初始化1
string sql_com = "select demno 校招编号,comjob 招聘名称 from Scdemand where comno = '{0}'";
sql_com = string.Format(sql_com, this.comno);
table = operation.ExecuteQuery(sql_com);
if(table != null)
{
    this.comboBox1.DataSource = table;
    //this.comboBox1.DisplayMember = "";//显示的值
    this.comboBox1.ValueMember = "校招编号";//对应的值
}
```
2. 妥协。设置两个属性，但是设置的方法有待注意！  
```C#
//组合框的初始化2
string sql1 = "select uniname 高校名称,unino 高校编号 from University where uniname like '%{0}%'";
sql1 = string.Format(sql1, content);
dataTable = databaseOperation.ExecuteQuery(sql1);
if (dataTable.Rows.Count > 0)//证明有数据，重新绑定数据
{
    this.comboBox1.DataSource = dataTable;
    this.comboBox1.DisplayMember = dataTable.Columns[0].ToString();//显示的值
    this.comboBox1.ValueMember = dataTable.Columns[1].ToString();//对应的值
    this.comboBox1.SelectedIndex = 0;
}

//组合框的初始化3
string sql_com = "select demno 校招编号,comjob 招聘名称 from Scdemand where comno = '{0}'";
sql_com = string.Format(sql_com, this.comno);
table = operation.ExecuteQuery(sql_com);
if(table != null)
{
    this.comboBox1.DataSource = table;
    this.comboBox1.DisplayMember = "招聘名称";//显示的值
    this.comboBox1.ValueMember = "校招编号";//对应的值
}
```
3. 如何获取组合框绑定之后被选择的数据项
```C#
//方式1
DataRowView drv = (DataRowView)comboBox1.SelectedItem;//Point!易错点！
string comno = drv.Row["comno"].ToString();//Point!易错点！
//方式2
string comno = Convert.ToString(this.combobox1.SelectValue);
```















