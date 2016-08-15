Unicode-Eyuyan
==============

一个进行 Unicode 相关字符串转换的易语言库。

An Eyuyan library dealing with Unicode string conversion.


背景 Background
---------------

[易语言](https://zh.wikipedia.org/wiki/%E6%98%93%E8%AF%AD%E8%A8%80)是一个面向初学者的编程语言，其源代码使用中文字符书写。然而，直至版本 5.5，易语言还在使用 Win32 ANSI API 处理字符串，迟迟未加入 Unicode 支持，给生僻汉字、外国文字处理带来不便。

[Eyuyan](https://en.wikipedia.org/wiki/Easy_Programming_Language) is a programming language for beginners, whose source code is written in Chinese characters. However, Eyuyan was always using Win32 ANSI API to process strings, and has never supported Unicode, which made it difficult to deal with multi-language context.


使用方法 Usage
--------------

笔者认为你已经有 C 等高级编程语言的基础，因为某些原因迫不利己而使用易语言。

因为 Windows 使用 UTF-16 Little Endian 来表示 Unicode 字符串，所以本库提供 UTF-8 和 ANSI 到 UTF-16 的转换。

在转换到 UTF-16 后，可以传入 Win32 Wide API 来使用。

```vb
.局部变量 我的ANSI字符串, 文本型
.局部变量 我的UTF8字符串, 字节集
.局部变量 转换自ANSI, 字节集
.局部变量 转换自UTF8, 字节集

' 定义一个 ANSI 字符串
我的ANSI字符串 ＝ “你好，世界！”

' 定义一个 UTF-8 字符串
我的UTF8字符串 ＝ { 228, 189, 160, 229, 165, 189, 239, 188, 129 }

' 把字符串转成 UTF-16
转换自ANSI ＝ ANSI转UTF16 (我的ANSI字符串)
转换自UTF8 ＝ UTF8转UTF16 (我的UTF8字符串)

' 调用 MessageBoxW 函数
MessageBoxW (0, 0, 字节集加零 (转换自ANSI), 字节集加零 (转换自UTF8), 64)
```


协议 License
------------

本库以 BSD 协议发布，参见随附的 LICENSE.txt 文件。

This library is released under BSD license. Please see the LICENSE.txt file, which is provided in this package.

