```C#
<Grid>
        <!--写列、写行-->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" MinWidth="87"></ColumnDefinition>
            <ColumnDefinition Width="371*"></ColumnDefinition>
            <ColumnDefinition Width="59*"/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
        </Grid.RowDefinitions>
        <Label Grid.Column="0" Grid.Row="0" HorizontalAlignment="Center" VerticalAlignment="Center"
                Width="70" Margin="8,14,9,14">消息内容：</Label>
        <Label Grid.Column="0" Grid.Row="1" HorizontalAlignment="Center" VerticalAlignment="Center"
                Width="46" Margin="20,14,21,14">标题：</Label>
        <Label Grid.Column="0" Grid.Row="2" HorizontalAlignment="Center"
                VerticalAlignment="Center" Width="46" Margin="20,14,21,14">按钮：</Label>
        <Label Grid.Column="0" Grid.Row="3" HorizontalAlignment="Center"
                VerticalAlignment="Center" Width="46" Margin="20,14,21,14">图标：</Label>
        <TextBox Grid.Column="1" Grid.Row="0" Name="messageBoxText" Grid.ColumnSpan="2" >消息内容</TextBox>
        <TextBox Grid.Column="1" Grid.Row="1" Name="caption" Grid.ColumnSpan="2">标题</TextBox>
        <StackPanel Grid.Column="1" Grid.Row="2" Orientation="Horizontal"
                VerticalAlignment="Center" Name="buttonStackPanel" Grid.ColumnSpan="2" Margin="0,20,0,19">
            <RadioButton IsChecked="True" Margin="10 0 10 0">OK</RadioButton>
            <RadioButton Margin="10 0 10 0">OKCancel</RadioButton>
            <RadioButton Margin="10 0 10 0">YesNo</RadioButton>
            <RadioButton Margin="10 0 10 0">YesNoCancel</RadioButton>
        </StackPanel>
        <StackPanel Grid.Column="1" Grid.Row="3" Orientation="Horizontal"
                VerticalAlignment="Center" Name="imageStackPanel" Grid.ColumnSpan="2" Margin="0,19,0,20">
            <RadioButton IsChecked="True" Margin="10 0 10 0">Error</RadioButton>
            <RadioButton Margin="10 0 10 0">Information</RadioButton>
            <RadioButton Margin="10 0 10 0">Question</RadioButton>
            <RadioButton Margin="10 0 10 0">Warning</RadioButton>
        </StackPanel>
        <Button Grid.Column="0" Grid.ColumnSpan="3" Grid.Row="4"
                Name="showMessageBoxButton"
                Click="showMessageBoxButton_Click">显示消息框</Button>
        <StatusBar Grid.Column="0" Grid.ColumnSpan="3" Grid.Row="5">
            <StatusBarItem>
                <TextBlock Name="resultTextBlock">Ready</TextBlock>
            </StatusBarItem>
        </StatusBar>
    </Grid>
```
