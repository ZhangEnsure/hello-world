效果示例：
![运行效果如下](https://github.com/ZhangEnsure/hello-world/blob/master/img-store/image.png)

```C#
<Window x:Class="ch08.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        
        WindowStartupLocation="CenterScreen" Title="WPF控件基本用法" Height="350"
        Width="600">
    <Grid>
        //我的理解是“第一列根据具体内容的宽度”进行调整
        //第二列根据实际情况进行全部占用
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition Width="*" />
        </Grid.ColumnDefinitions>
        //首先声明一个TreeView类型的一个数据显示
        <TreeView Grid.Row="0" Grid.Column="0"
                //随后声明一个树状类型的项目的事件
                TreeViewItem.Selected="TreeViewItem_Selected"
                //在随后的垂直滚动条选择可见，特别注意要声明为ScrollViewer的Vertical...
                ScrollViewer.VerticalScrollBarVisibility="Visible"
                Margin="0,0,0,0">
            <TreeViewItem Header="常用属性" Tag="BasicProperty">
                <TreeViewItem Header="MarginPadding" />
                <TreeViewItem Header="HorizontalAlignmentPage" />
                <TreeViewItem Header="VerticalAlignmentPage" />
            </TreeViewItem>
            <TreeViewItem Header="常用布局控件" Tag="LayoutControls">
                <TreeViewItem Header="GridPage" />
                <TreeViewItem Header="StackPanelPage" />
                <TreeViewItem Header="CanvasPage" />
                <TreeViewItem Header="BorderPage" />
                <TreeViewItem Header="DockPanelPage" />
                <TreeViewItem Header="BulletDecoratorPage" />
                <TreeViewItem Header="ExpanderPage" />
                <TreeViewItem Header="GridSplitterPage" />
                <TreeViewItem Header="GroupBoxPage" />
            </TreeViewItem>
            <TreeViewItem Header="常用基本控件" Tag="BasicControls">
                <TreeViewItem Header="ButtonPage" />
                <TreeViewItem Header="TextBoxPasswordBox" />
                <TreeViewItem Header="RadioButtonPage" />
                <TreeViewItem Header="CheckBoxPage" />
                <TreeViewItem Header="ListBoxComboBox" />
            </TreeViewItem>
            <TreeViewItem Header="菜单工具条状态条" Tag="MenuControls">
                <TreeViewItem Header="MenuContextMenu" />
                <TreeViewItem Header="ToolBarStatusBar" />
            </TreeViewItem>
            <TreeViewItem Header="图像和GIF动画" Tag="OtherControls">
                <TreeViewItem Header="ImageExamplePage" />
                <TreeViewItem Header="WindowsFormsHostPage" />
            </TreeViewItem>
        </TreeView>
        //表格分割条，可以左右拖动
        <GridSplitter Grid.Row="0" Grid.Column="0" BorderBrush="Gray"
                BorderThickness="1" ResizeBehavior="CurrentAndNext" />
        //声明了一个Padding属性，并且设置水平和垂直的拉伸
        <Frame Name="frame1" Grid.Row="0" Grid.Column="1"
                Padding="10 20 10 20" HorizontalAlignment="Stretch"
                VerticalAlignment="Stretch" NavigationUIVisibility="Hidden" />
    </Grid>
</Window>
```
