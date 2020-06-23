## 属性
1. 在界面中对Rectangle图形进行操作、做出各种变换，最后想操作结束后将原图形回复原型。
可以设计一个RectTag类型的对象rectTag，此对象保存对矩形操作前的图形原始信息。代码示例如下：
2. 注意，需要提前定义一个RectTag类。
```C#
//定义一个RectTag类
public class RectTag
{
    public System.Windows.Media.Brush RectFillBrush { get; set; }
    public double RectOpacity { get; set; }
}

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
对于我自己而言，FrameworkElement类型类似var一样，既然是在画布中声明的事件方法，根据路由机制，在画布中的子元素也同样的注册了
相同的事件，在使用的过程中也就要写通用的代码进行操作。</br> **注意**：
sender就是注册时的控件，而e.OriginalSource或e.Source是实际触发时的控件。
```C#
private void ParentCanvas_MouseMove(object sender, MouseEventArgs e)
{
    FrameworkElement senderElement = sender as FrameworkElement;
    FrameworkElement sourceElement = e.OriginalSource as FrameworkElement;
    FrameworkElement sourceObject = e.Source as FrameworkElement;
    Rectangle rect = e.Source as Rectangle;
    Point p = Mouse.GetPosition(null);//既然是null，则是相对于窗口最左上角的位置进行计算
    ellipse.Width = p.X;
    ellipse.Height = p.Y;
    statusTextBlock.Text = string.Format(
        "发送事件的对象：{0}\t事件源：{1}\t引发事件的对象：{2}\n鼠标位置：x={3}, y={4}",
        senderElement.Name, sourceElement.Name, sourceObject.Name, p.X, p.Y);
}
```





















