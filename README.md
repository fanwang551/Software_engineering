# 代码修改
常见规范问题：
1. 函数和方法的名称后面没有留空格。
2. if、elif、try、except、for、while和with语句后面没有留空格。
3. 一些行太长，并且没有分行。
4. 变量名没有描述变量所表示的内容。
5. 缺少适当的注释来解释代码的行为。
6. 代码中有一些无用的符号，例如制表符和多个空格。

## word_dict.py修改
>函数功能：构建初步词典和最终词典，它使用了两个语料库，其中包含Python和SQL代码的数据。程序使用了一些函数来加载和处理数据，包括load_json和load_pickle函数来加载JSON和pickle文件，get_vocab函数来构建词典，save_json函数来保存数据到JSON文件中，以及vocab_processing和final_vocab_processing函数来构建初步词典和最终词典。

1. 在函数和变量命名时，应该遵循PEP8规范，即使用小写字母和下划线来分隔单词。
2. 代码注释应该尽可能描述代码的功能和作用，避免使用没有意义的注释。
3. 应该使用with语句来打开文件，这样可以在操作完成后自动关闭文件，避免程序出现异常时文件未关闭的情况。
4. 在函数定义时，应该添加docstring来描述函数的功能和参数等信息。 
5. 在代码中使用空格和缩进来使代码更易于阅读，应该遵循PEP8规范的缩进方式。
6. 应该避免使用eval函数来读取文件，因为会存在安全性问题。可以使用json或者pickle来代替eval。
7. 在代码中应该避免使用硬编码，将路径等信息定义为变量或常量会使代码更易于维护。
## 
修改：

1. 函数和变量的命名可以更好地描述其功能和用途，例如将`filter_part_invachar`改为`filter_invalid_characters`，`process_nl_line`应改为`process_nl_line`，`tags_dict`改为`tags_dict`。
2. 部分函数的注释可以更加详细和准确，方便其他人理解代码的功能和实现。
3. 变量的命名方式尽量保持一致，例如`typedCode`和`token_list`可以都改为下划线形式的命名。
4. 函数体内的代码可以在一行内时进行合并，提高代码可读性。
5. 运算符：括号内不应该加空格，括号后要加空格；如`word_pos in ['a', 'v', 'n', 'r']`应改为`word_pos in ['a', 'v', 'n', 'r']`；
6. 字符串拼接：字符串拼接时，应使用加号或者格式化语法；如`line=' '.join(line)`应该改为`line = ' '.join(line)`；

##
1. 缺少函数、变量、参数的注释说明；
2. 函数名应该使用小写字母，单词之间以下划线分隔，例如`python_parser`；
3. 函数名要避免使用关键词或系统保留字，例如`revert_abbrev`应该改为`restore_abbrev`；
4. 缺少空格，例如`bool_failed_var = False`应该改为`bool_failed_var=False`；
5. 连续的操作符或操作符与操作数之间应该加空格，例如`if candidate not in varnames:`应该改为`if candidate not in varnames: `;
6. 使用单引号或双引号要统一，不能混用，例如`'NUMBER', 'STRING', 'NEWLINE'`应该改为`"NUMBER", "STRING", "NEWLINE"`；
7. 函数代码缩进不一致，应该保持一致，通常是四个空格缩进；
8. 变量名应该使用小写字母，单词之间以下划线分隔，例如`bool_failed_var`应该改为`bool_failed_variable`；
9. 不建议在 try-except 块中使用空 except，在 except 后应该指定具体的异常类型；
10. 没有引入需要的模块，例如在函数中调用了`get_vars`、`repair_program_io`、`wordpunct_tokenize`，但并没有引入相关的模块，需要在文件头部引入；
11. 除了在被函数内部调用的模块，在其他地方最好避免使用 import *；
这段代码存在以下规范问题：

##
(语料处理)[./codecs/data_processing/hnn_process/process_single_corpus.py]
>这个程序是主要用于对语料进行处理。它包含了三个函数：load_pickle、single_list和data_staqc_prpcessing。其中load_pickle函数用于加载pickle文件，single_list函数用于计算一个列表中某个元素出现的次数，data_staqc_prpcessing函数用于将语料中的单候选和多候选分开。在if name == "main"中，程序调用了data_staqc_prpcessing函数和data_large_prpcessing函数，将staqc_python中的单候选和多候选分开，将staqc_sql中的单候选和多候选分开，将large_python中的单候选和多候选分开，将large_sql中的单候选和多候选分开，并将单候选只保留其qid。最终结果会保存在指定的文件中。



该代码做了以下修改:
1. 使用更有意义的变量名和函数名
2. 添加了注释来解释函数的作用
3. 使用json.load()代替eval()加载数据
4. 抽取了重复逻辑到process_data()函数中
5. 使用常量替换文件路径
6. 使用注释解释主要逻辑
7. 抽取重复调用process_data()的逻辑到一个循环中

##
1. 缺少注释。这个程序虽然不算很复杂,但是注释还是很重要的,可以帮助其他人理解代码逻辑。
2. 命名不规范。像 split_num 这种变量名不太明显,可以改成更有意义的名称,比如 batch_size。某些 magic number 也可以提取成常量,比如 words_top = 100。
3. 重复代码太多。parse_python 和 parse_sqlang 这两个函数有很多重复的逻辑,可以提取出来放在一个公共函数中。
4. 主函数 main 过于简单,逻辑可以抽取成更小的函数。现在 main 函数里面 if-else 分支太多,可读性不高。
5. 文件路径作为 "魔法字符串" 编写在代码中,不太规范。可以提取成配置文件或常量。
6. 可以添加一些异常处理,现在程序如果文件路径错误等就会直接崩溃。
修改 :
1. 添加更多注释,特别是在逻辑比较复杂的地方。
2. 给变量和常量以更有意义的命名。
3. 提取公共逻辑到函数中,减少重复代码。
4. 将 main 函数逻辑拆分成多个小函数。
5. 将文件路径提取成配置文件或常量。
6. 添加异常处理机制,增加程序健壮性。
7. 可以考虑使用日志工具进行日志记录,方便调试和维护。
8. 根据 PEP8 规范进一步规范代码风格。

##
1. 缺少注释，不利于代码的理解和维护。
2. 函数和变量命名不符合PEP8规范，应该使用小写字母和下划线的组合。
3. `with open(type_word_path,'r')as f:` 这一行应该使用上下文管理器来打开文件，并且应该使用`with open(type_word_path,'r', encoding='utf-8') as f:`来指定编码方式。
4. `eval()`函数不安全，可以使用`json`替代。
5. 在`get_index`函数中，可以使用`word_dict.get(text[i],'UNK')`来避免使用`None`。
6. 在`Serialization`函数中，可以将`len(Si_word_list)`和`len(Si1_word_list)`的代码提取为一个函数进行复用。
7. `block_length`和`label`这两个变量应该在函数参数中进行传递，而不是函数内部进行赋值。
8. 在`get_new_dict`函数中，应该使用`with open`来打开文件，而不是直接使用`open`，并且应该使用`json`来替代`eval()`函数。
9. `total_data`这个变量名意义不明确，可以使用`serialized_data`来增加代码的可读性。
10. 函数的参数命名缺失很多变量的类型信息，比如`word_dict_path`是什么类型的。
11. `pad_embedding`等变量名命名过长，可以使用`pad`, `unk`等缩写来增加代码的可读性。
12. `get_index` 函数中`type`参数应该改名为`input_type`，以避免与Python的`type()`函数产生歧义。

添加了函数文档字符串，方便了解每个函数的目的。
改进了变量名以更好地表达它们的含义。
使用统一的命名约定来提高代码的可读性。
使用黑板格式来提高代码的可读性。
删除了未使用的变量。
将字符串连接符改为 f-strings 以提高可读性。
添加了 try-except 语句以捕获任何加载单词的词向量时发生的异常。
改进了一些打印语句，以便更易读。
