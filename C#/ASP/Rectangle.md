## 属性
1. 在界面中对Rectangle图形进行操作、做出各种变换，最后想操作结束后将原图形回复原型。
可以设计一个RectTag类型的对象rectTag，此对象保存对矩形操作前的图形原始信息。代码示例如下：
```C#
private void Rect_MouseEnter(object sender, MouseEventArgs e)
{
    Mouse.OverrideCursor = Cursors.Hand;
    Rectangle rect = e.Source as Rectangle;//获取事件源的图形
    RectTag rectTag = new RectTag();//声明一个RectTag类型的对象保存对事件源操作前的原始信息
    //利用RectTag对象保留了原始矩形的填充色和不透明度
    rectTag.RectFillBrush = rect.Fill;
    rectTag.RectOpacity = rect.Opacity;//指的是不透明度
    rect.Tag = rectTag;//有关于此元素的自定义信息的任意对象值
    rect.Fill = Brushes.Red;
}
```

鼠标退出图形之后
```C#
private void Rect_MouseLeave(object sender, MouseEventArgs e)
{
    Mouse.OverrideCursor = Cursors.Arrow;
    Rectangle rect = e.Source as Rectangle;
    RectTag rectTag = rect.Tag as RectTag;
    rect.Fill = rectTag.RectFillBrush;
    rect.Opacity = rectTag.RectOpacity;
}
```






















