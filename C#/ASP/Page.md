# 知识点
1. 承载Page页的window窗体选择
```C#
w = new System.Windows.Navigation.NavigationWindow();
w.Content = new PageExamples.Page1();
```
2. 一个Page页转跳另一个Page页的超链接形式
<TextBlock HorizontalAlignment="Center">
  <Run>单击</Run>
  <Hyperlink NavigateUri="Page2.xaml">此处</Hyperlink>
  <Run>测试超链接，观察是否有反应！</Run>
</TextBlock>



