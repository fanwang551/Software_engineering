# 代码修改

## word_dict.py修改
>函数功能：构建初步词典和最终词典，它使用了两个语料库，其中包含Python和SQL代码的数据。程序使用了一些函数来加载和处理数据，包括load_json和load_pickle函数来加载JSON和pickle文件，get_vocab函数来构建词典，save_json函数来保存数据到JSON文件中，以及vocab_processing和final_vocab_processing函数来构建初步词典和最终词典。

1. 在函数和变量命名时，应该遵循PEP8规范，即使用小写字母和下划线来分隔单词。
2. 代码注释应该尽可能描述代码的功能和作用，避免使用没有意义的注释。
3. 应该使用with语句来打开文件，这样可以在操作完成后自动关闭文件，避免程序出现异常时文件未关闭的情况。
4. 在函数定义时，应该添加docstring来描述函数的功能和参数等信息。 
5. 在代码中使用空格和缩进来使代码更易于阅读，应该遵循PEP8规范的缩进方式。
6. 应该避免使用eval函数来读取文件，因为会存在安全性问题。可以使用json或者pickle来代替eval。
7. 在代码中应该避免使用硬编码，将路径等信息定义为变量或常量会使代码更易于维护。


