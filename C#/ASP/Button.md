# 知识点
1. Button有两个属性IsDefault和IsCancel.
2. IsDefault是取得或设定值，这个值表示Button是否为预设按钮。使用者可按ENTER键来叫用预设按钮。如果Button是预设按钮，则为true，否则为false。预设值为false.
```C#
public bool IsDefault { get; set; }
```
3. IsCancel是取得或设定值，这个值表示Button是否为[取消]按钮。使用者按一下ESC键，就可以启用[取消]按钮。如果Button是[取消]按钮，则为true，否则为false。预设值为false。
```C#
public bool IsCancel { get; set; }
```
