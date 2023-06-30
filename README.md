# 代码修改
常见规范问题：
1. 函数和方法的名称后面没有留空格。
2. if、elif、try、except、for、while和with语句后面没有留空格。
3. 一些行太长，并且没有分行。
4. 变量名没有描述变量所表示的内容。
5. 缺少适当的注释来解释代码的行为。
6. 代码中有一些无用的符号，例如制表符和多个空格。

## word_dict.py修改
[word_dict.py](./codecs/data_processing/hnn_process/word_dict.py)
>函数功能：构建初步词典和最终词典，它使用了两个语料库，其中包含Python和SQL代码的数据。程序使用了一些函数来加载和处理数据，包括load_json和load_pickle函数来加载JSON和pickle文件，get_vocab函数来构建词典，save_json函数来保存数据到JSON文件中，以及vocab_processing和final_vocab_processing函数来构建初步词典和最终词典。

1. 在函数和变量命名时，应该遵循PEP8规范，即使用小写字母和下划线来分隔单词。
2. 代码注释应该尽可能描述代码的功能和作用，避免使用没有意义的注释。
3. 应该使用with语句来打开文件，这样可以在操作完成后自动关闭文件，避免程序出现异常时文件未关闭的情况。
4. 在函数定义时，应该添加docstring来描述函数的功能和参数等信息。 
5. 在代码中使用空格和缩进来使代码更易于阅读，应该遵循PEP8规范的缩进方式。
6. 应该避免使用eval函数来读取文件，因为会存在安全性问题。可以使用json或者pickle来代替eval。
7. 在代码中应该避免使用硬编码，将路径等信息定义为变量或常量会使代码更易于维护。
## sqlang_structured.py修改
[sqlang_structured.py](./codecs/data_processing/hnn_process/sqlang_structured.py)
修改：

1. 函数和变量的命名可以更好地描述其功能和用途，例如将`filter_part_invachar`改为`filter_invalid_characters`，`process_nl_line`应改为`process_nl_line`，`tags_dict`改为`tags_dict`。
2. 部分函数的注释可以更加详细和准确，方便其他人理解代码的功能和实现。
3. 变量的命名方式尽量保持一致，例如`typedCode`和`token_list`可以都改为下划线形式的命名。
4. 函数体内的代码可以在一行内时进行合并，提高代码可读性。
5. 运算符：括号内不应该加空格，括号后要加空格；如`word_pos in ['a', 'v', 'n', 'r']`应改为`word_pos in ['a', 'v', 'n', 'r']`；
6. 字符串拼接：字符串拼接时，应使用加号或者格式化语法；如`line=' '.join(line)`应该改为`line = ' '.join(line)`；

## python_structured.py修改
[python_structured.py](./codecs/data_processing/hnn_process/python_structured.py)
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

## process_single_corpus.py修改
[process_single_corpus.py](./codecs/data_processing/hnn_process/process_single_corpus.py)
>这个程序是主要用于对语料进行处理。它包含了三个函数：load_pickle、single_list和data_staqc_prpcessing。其中load_pickle函数用于加载pickle文件，single_list函数用于计算一个列表中某个元素出现的次数，data_staqc_prpcessing函数用于将语料中的单候选和多候选分开。在if name == "main"中，程序调用了data_staqc_prpcessing函数和data_large_prpcessing函数，将staqc_python中的单候选和多候选分开，将staqc_sql中的单候选和多候选分开，将large_python中的单候选和多候选分开，将large_sql中的单候选和多候选分开，并将单候选只保留其qid。最终结果会保存在指定的文件中。



该代码做了以下修改:
1. 使用更有意义的变量名和函数名
2. 添加了注释来解释函数的作用
3. 使用json.load()代替eval()加载数据
4. 抽取了重复逻辑到process_data()函数中
5. 使用常量替换文件路径
6. 使用注释解释主要逻辑
7. 抽取重复调用process_data()的逻辑到一个循环中

## getStru2Vec.py 修改
[getStru2Vec.py](./codecs/data_processing/hnn_process/getStru2Vec.py)
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

## embddings_process.py 修改
[embddings_process.py](./codecs/data_processing/hnn_process/embddings_process.py)
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

# models_text.py 修改
[models_text.py](./codecs/ANN_Staqc_new/hnn/models_text.py)
1. 缺少模块导入语句的换行，可以在每个导入语句之后添加一个空行。
2. 缺少函数之间的空行分隔，可以在每个函数之间添加空行以提高可读性。
3. 缩进不一致，有些地方使用了4个空格缩进，有些地方使用了8个空格缩进，应该保持统一。
4. 缺少注释解释每个函数的功能和输入输出。
5. 变量命名不规范，例如`text_S1`、`text_S2`、`code`等变量应该使用小写字母开头的驼峰命名法。
6. 缺少异常处理，例如在文件读取部分没有处理文件不存在或无法打开的情况。
7. 导入的模块和类名没有按照惯例使用小写字母开头。
8. 函数参数列表没有按照惯例使用小写字母开头的下划线分隔命名法。
9. 缺少函数的返回类型注释。
10. 使用了不推荐使用的`tf.compat.v1.disable_eager_execution()`函数。
11. 函数`params_adjust`中的参数名不具有描述性，应该使用更具体的参数名。
12. 函数`build`中存在未使用的变量。
13. 函数`build`中存在未使用的参数。
14. 函数`build`中的代码缺少注释解释每个步骤的功能。
15. 函数`compile`和`fit`中的参数名不具有描述性，应该使用更具体的参数名。
16. 函数`example_loss`中的参数名不具有描述性，应该使用更具体的参数名。
17. 函数`example_loss`中的`print`语句应该删除。
18. 函数`dice_coef`和`dice_loss`中的参数名不具有描述性，应该使用更具体的参数名。
19. 函数`dice_loss`中的`P_loss`变量没有使用，可以删除。
20. 函数`dice_loss`中的`dice`函数应该添加参数类型注释。
21. 函数`dice`中的`dice_coef`函数调用缺少参数。
22. 函数`dice`中的`return`语句缺少返回值。
23. 函数`__init__`中的一些变量没有使用，可以删除。
24. 函数`__init__`中的参数名不具有描述性，应该使用更具体的参数名。
25. 函数`params_adjust`中的参数名不具有描述性，应该使用更具体的参数名。
26. 缺少对模型中每个层的参数设置的注释解释。
27. 缺少对模型中每个层的连接关系的注释解释。

# model.py
[models.py](./codecs/ANN_Staqc_new/hnn/models.py)
1. 代码中有很多导入的包没有使用，比如`import os`，`import logging`等。
2. 在代码的开头使用了`__future__`模块来导入一些新版本的功能，但是在后面并没有使用这些新功能，比如`print_function`和`absolute_import`。
3. 在导入`tensorflow`相关模块时，有的使用了`from tensorflow.keras.models import Model`，有的使用了`import tensorflow as tf`，不够统一。
4. 在导入自定义的模块时，比如`concactLayer`，`mediumlayer`，`attention_layer`等，应该使用绝对路径或者相对路径来导入，而不是直接使用模块名。
5. 在代码中有多处使用了`print()`函数来打印调试信息，这样的方式不够规范，应该使用日志模块来记录日志信息。
6. 类的命名不符合规范，应该使用大写字母开头的驼峰命名法，比如`CodeMF`应该改为`CodeMF`。
7. 函数命名不符合规范，应该使用小写字母开头的下划线命名法，比如`params_adjust`应该改为`params_adjust`。
8. 代码中有很多硬编码的参数，比如`self.text_length = 100`，`self.queries_length = 25`，这些参数应该通过配置文件或者函数参数来传递。
9. 在代码中定义了很多类成员变量，但是并没有使用。
10. 函数`build()`中的注释不够准确，应该描述函数的功能和输入输出。
11. 函数`fit()`中的参数`x`和`y`的类型没有指定。
12. 函数`save()`和`load()`中的参数`class_model_file`的类型没有指定。
13. 函数`mycrossentropy()`和`dice_coef()`中的参数`e`的含义没有明确说明。
14. 在函数`example_loss()`中使用了`tf.compat.v1.nn.softmax_cross_entropy_with_logits()`函数，但是这个函数已经被弃用了，应该使用`tf.nn.softmax_cross_entropy_with_logits()`。
15. 函数`example_loss()`中的`reduce_sum()`函数的参数类型不正确，应该是`axis=0`，而不是`axis=1`。
16. 函数`dice_loss()`中的`dice_coef()`函数的参数`p1`，`p2`，`p3`，`p4`没有在函数中使用。
17. 在函数`dice_loss()`中定义了内部函数`dice()`，但是没有在函数中使用。
18. 函数`dice_loss()`中的`categorical_crossentropy()`函数的参数类型不正确，应该是`from_logits=True`，而不是`from_logits=False`。
19. 函数`dice_loss()`中的`K.categorical_crossentropy()`函数的参数类型不正确，应该是`axis=1`，而不是`axis=0`。
20. 函数`dice_loss()`中的`K.ones_like()`函数的参数类型不正确，应该是`tf.shape(y_pred)`，而不是`K.shape(y_pred)`。


# mian.py
[main.py](./codecs/ANN_Staqc_new/hnn/main.py)
1. 缺少必要的import语句，例如`import sys`和`import pickle`。
2. 在`import logging`之后没有设置logging的级别和格式。
3. 在代码的开头使用了`from __future__ import print_function`，这是为了兼容Python 2和Python 3的写法。但是在该程序中，并没有使用到Python 2的特性，因此可以将该行代码删除。
4. 在代码中有一些被注释掉的import语句，这些语句应该被删除，以免混淆读者。
5. 在代码中有一些被注释掉的设置随机种子的语句，这些语句应该被删除，因为已经在代码中使用了固定的种子值。
6. `set_session`函数在导入时并未使用，因此可以删除。
7. 在`StandoneCode`类的构造函数中，存在一个不规范的命名，应该将`conf`改为`configs`。
8. 在`StandoneCode`类中，`self._buckets_text_max`和`self._buckets_code_max`的计算方式可以简化，可以直接使用`max(self._buckets, key=lambda x: x[0])`和`max(self._buckets, key=lambda x: x[2])`。
9. 在`StandoneCode`类中的`load_pickle`函数中，应该将`return word_dict`改为`return word_dict`。
10. 在`StandoneCode`类中的`pad`函数中，应该将`return pad_sequences(data, maxlen=len, padding='post', truncating='post', value=0)`改为`return pad_sequences(data, maxlen=len, padding='post', truncating='post', value=0)`。
11. `StandoneCode`类中的`get_data`函数中存在一些错误，例如`text_S1`和`text_S2`应该使用`extend`方法而不是`append`方法，`id`应该改为`ids`。
12. 在`StandoneCode`类中的`train`函数中，`hist = model.fit([np.array(text_S1), np.array(text_S2), np.array(code), np.array(queries)], np.array(labels), shuffle=True, epochs=1, batch_size=batch_size)`语句中，`hist`并未使用，可以将其删除。
13. `StandoneCode`类中的`valid`函数中，应该将`return acc, f1,recall,precision,loss`改为`return acc, f1, recall, precision, loss`。
14. `parse_args`函数中，`parser.add_argument("--verbose",action="store_true", default=True, help="Be verbose")`语句中，`action="store_true"`应该改为`action="store_false"`，因为默认为True，所以在调用时不需要加上`--verbose`参数来开启。
15. 在`if __name__ == '__main__':`语句中，`conf = get_config(args.train)`应该改为`conf = get_config(args.train.lower())`，因为`get_config`函数接受的参数是小写的字符串。
16. 在`if __name__ == '__main__':`语句中，`model.params_adjust(dropout1=drop1, dropout2=drop2, dropout3=drop3, dropout4=drop4, dropout5=drop5, Regularizer=round(r, 5), num=8, seed=42)`语句中，`Regularizer`应该改为`regularizer`。
17. 在`if __name__ == '__main__':`语句中，`conf['training_params']['regularizer'] = round(r, 5) + 1`语句应该删除，因为已经在上一行设置过了。
18. 在`if __name__ == '__main__':`语句中，`model.build()`应该改为`model.build_model()`，因为没有定义`build`方法。
19. 在`if __name__ == '__main__':`语句中，`StandoneCode.load_model_epoch(model, 121, 0.5, 0.5, 0.5, 0.5, 0.0006)`和`StandoneCode.load_model_epoch(model, 83, 0.25, 0.25, 0.25, 0.25, 0.0006)`语句中的参数顺序应该改为`d12, d3, d4, d5, r`。
20. 在`if __name__ == '__main__':`语句中，`StandoneCode.eval(model, test_path)`语句中，`test_path`应该改为`dev_path`，以评估开发集而不是测试集。

# MultiHeadAttention.py
[MultiHeadAttention.py](./codecs/ANN_Staqc_new/hnn/MultiHeadAttention.py)
1. 代码中导入了重复的库，例如tensorflow和numpy被导入了两次。
2. 代码中定义了一些不必要的变量，例如`self.intensity`和`self.attention`在`ScaledDotProductAttention`类中被定义，但没有被使用。
3. 类名`MultiHeadAttention_`不符合Python的命名规范，应该使用驼峰命名法，即`MultiHeadAttention`。
4. 缺少注释来解释代码的功能和逻辑。
5. 没有提供示例代码的用法和预期输出，导致阅读代码时缺少上下文信息。
6. 代码中使用了硬编码的数字，例如`head_num`和`feature_dim`，应该使用变量或参数来表示这些值，以增加代码的可读性和灵活性。
7. 缺少异常处理，例如在`build`方法中没有处理输入维度不匹配的情况。
8. 代码中的一些命名不够清晰和描述性，例如`q`、`k`、`v`等变量名，可以使用更具描述性的名称来增加代码的可读性。
9. 使用了混合的导入风格，有些地方使用了`import tensorflow as tf`，有些地方使用了`from tensorflow import *`，应该保持一致性并使用标准的导入风格。
10. 缺少对代码中使用的数学公式和算法的解释，使得阅读代码时不容易理解其背后的原理和目的。
