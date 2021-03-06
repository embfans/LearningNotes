[原文链接：TextView之空格占位法](https://www.jianshu.com/p/3afbaa5a2ab5?utm_campaign=haruki&utm_content=note&utm_medium=reader_share)

## 使用空格占位实现文字对齐

```xml
&#32; == 普通的英文半角空格

&#160; == &nbsp; == &#xA0; == no-break space （普通的英文半角空格但不换行）

&#12288; == 中文全角空格 （一个中文宽度）

&#8194; == &ensp; == en空格 （半个中文宽度）

&#8195; == &emsp; == em空格 （一个中文宽度）

&#8197; == 四分之一em空格 （四分之一中文宽度）
```


* 空格： `&#160;`
* 窄空格： `&#8201;`
* 一个汉字宽度的空格：`&#160;&#160;&#8201;`

用两个空格 `&#160;&#160;` 占一个汉字的宽度时，两个空格比一个汉字略窄，三个空格 `&#160;&#160;&#160;` 比一个汉字略宽

在实际使用中需要灵活使用 和 的组合。

```xml
android:text="真实姓名:"
android:text="身&#160;&#160;份&#160;&#160;证:"
```


```xml
android:text="姓& #160;& #160;& #8201;名:"
android:text="身份证:"
```


## TextView实现首行缩进的方法：

* 在 string 资源文件中，在文字的前面加入 `\u3000\u3000` 即可实现首行缩进
* 在 Java 代码中，使用 `setText("\u3000\u3000"+xxxxx);`

