# 前言
1. 有的时候在应用RadioButton的时候常常配合一个Button按钮作为一个最后选择的触发条件。故可以在写Button的Click
事件时写一个循环，判断哪一个单选按钮被选择。
## 使用的注意事项
把一组的RadioButton放在一个只包含RadioButton类型的面板中最好。
```c#
foreach (var item in buttonStackPanel.Children)
{
    RadioButton r = item as RadioButton;
    if (r.IsChecked == true)
    {
        //相关处理
    }
}
```
2. 写一个RadioButton的事件RadioButton_Checked，再声明一个变量配合即可。
```C#
RadioButton rb = null;
//别忘了注册
private void RadioButton_Checked(object sender, RoutedEventArgs e)
{
    rb = e.Source as RadioButton;
}
```
