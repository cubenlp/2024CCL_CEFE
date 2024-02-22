# 2024CCL_CEFE

# 最新消息

| 时间 | 消息 |
| --- | --- |
| 2月1日 | [评测任务报名](https://docs.qq.com/form/page/DQnR5WWR2Tm50QlJZ) 训练数据将通过邮件的方式发送给各个参赛队伍|


# 0 最近Deadline：

更多相关时间信息详见5.1赛程。

| ddl | 消息 |
| --- | --- |
| 3月2日 | 发送训练数据给参赛队伍 |
| 3月31日 | 报名截止 |
| 4月1日 | 通过邮件的方式将测试集和结果提交链接发送给报名队伍，提交结果榜单详见各赛道Github主页|
| 5月15日 | 测试集结果提交截止 |

# 1 组织者与联系人

&emsp;&emsp;任务组织者：庄薪霖（华东师范大学，计算机科学与技术学院），沈新舒（华东师范大学，计算机科学与技术学院），伍洪意（华东师范大学，计算机科学与技术学院），柏晓鹏（华东师范大学，中国语言文学系），兰曼（华东师范大学， 计算机科学与技术学院），吴苑斌（华东师范大学， 计算机科学与技术学院），毛绍光（微软亚洲研究院），夏炎（微软亚洲研究院）

&emsp;&emsp;任务联系人：庄薪霖（华东师范大学，zhuangxinlin2022@163.com）

# 2 任务内容

&emsp;&emsp;随着教育的发展和网络的普及，作文评价的规模越来越大，人工评改作文的成本和效率成为一大难题。为了解决这一问题，许多研究者和机构开始探索利用计算机技术来实现作文的自动评改[1]，通过分析作文的语言、内容、结构等方面的特点及存在的问题，给出客观、准确、及时的评分和反馈。其中，表述是否流畅是教师评改作文的一项重要内容。

&emsp;&emsp;作文流畅性反映一篇作文的通顺程度和语言使用的规范性，以及作者的写作水平和表达能力[2]，对提高作文评改质量、提升作者写作水平具有重要意义。目前，针对作文流畅性评价的研究工作通常从句子长度、词汇复杂度、句子结构等语言学特征角度进行评分或评级[2][3][4][5]；或是作为语法纠错任务，对句子中出现的拼写错误或语法错误进行识别和纠正[3][4]；或是视为病句判断任务[6]，判断一条句子是否是病句；这些方法通常将作文流畅性评估作为一个单独的自然语言处理任务，缺乏多层次、多角度的系统性整合；在对语法错误类型的定义上，以往的工作研究了赘余、缺失、误用、乱序四个粗粒度类别，缺乏更细粒度的错误类型定义；同时，他们的方法不具备良好的可解释性，没有定义作文流畅性评价的细粒度分项，无法对中小学生错误修改给出针对性的指导和修改意见。此外，

&emsp;&emsp;本次评测数据集来源于以汉语为母语的中小学生考试作文，区别于使用基于规则生成或汉语学习者的中介语数据中的错误[7]，以及其他类型母语者的口语、书面语的语法错误，中小学生作文中出现的错误类型更丰富，涉及的语法知识更复杂。因此我们的任务研究中小学生考试作文中的语法错误识别与纠正问题，系统地定义了影响作文流畅性的细粒度错误类型，并给出了修正建议，这种细粒度错误类型的定义与识别能够帮助学生更清楚地了解自己的写作问题，而修正建议能帮助学生更好地修改自己的作文，同时帮助教师更便捷地了解学生写作水平，有助于教师更好地指导学生写作。

&emsp;&emsp;基于此，本次评测任务从词法、句法、语义等多角度对作文流畅性进行详细分析，并给出修改建议，包括：

&emsp;&emsp;&emsp;&emsp;1、中小学作文病句类型识别；

&emsp;&emsp;&emsp;&emsp;2、中小学作文病句改写；

&emsp;&emsp;&emsp;&emsp;3、中小学作文流畅性评级；

&emsp;&emsp;共3个赛道，为中小学作文流畅性评改提供更多依据，提供更高质量的作文流畅性评估。

与去年相比，今年我们提供了更丰富的数据、更多样的赛道以及更丰厚的奖励，欢迎大家积极参与。

## 2.1 赛道1：中小学作文病句类型识别

- 任务描述：

&emsp;&emsp;由于中小学生写作能力有限，在作文写作时不可避免地会出现词法、句法上的病句，比如句子过长或过短，没有合理的停顿，或者使用了不恰当的词汇和语法。因此识别作文中的病句对学生发现自己错误、提升自己写作水平具有重要意义，也是作文流畅性评价、作文评改的一项重要指标。与出现在语文考试中的病句不同，本次评测中涉及的作文中的病句主要是指在词法、句法上有毛病的句子，病句的存在会降低文章的可读性和表达力，影响文章的质量和效果。以往针对病句的研究将病句识别定义为二分类任务[6]，即判断一个句子是否是病句。然而病句存在多种类型，不同错误类型能够反映作者存在不同的写作问题，以往的做法并不能具体指出作者所犯的错误，也无法帮助作者修改作文和提升作者的写作水平。本次评测从字符级错误和成分级错误两大角度出发，定义了字符级错误、成分残缺型错误、成分赘余型错误、成分搭配不当型错误和不合逻辑共5类粗粒度错误类型，以及缺字漏字、错别字错误、缺少标点、错用标点、主语不明、谓语残缺、宾语残缺、其他成分残缺、主语多余、虚词多余、其他成分多余、语序不当、动宾搭配不当、其他搭配不当等14种细粒度错误类型，对中小学作文中出现的病句类型进行研究。

- 任务定义：

&emsp;&emsp;中小学作文病句类型识别是一个多标签分类问题，预测一条句子是哪些类型的病句。病句类型标签同时包含词法、句法错误，本次评测任务共定义5个粗粒度错误类型和14个细粒度错误类型。病句类别定义及示例如下表1：
![表1 中小学作文病句类型识别赛道病句类型](https://github.com/cubenlp/2023CCL_CEFE/blob/main/imgs/%E8%A1%A81%20%E4%B8%AD%E5%B0%8F%E5%AD%A6%E4%BD%9C%E6%96%87%E7%97%85%E5%8F%A5%E7%B1%BB%E5%9E%8B%E8%AF%86%E5%88%AB%E8%B5%9B%E9%81%93%E7%97%85%E5%8F%A5%E7%B1%BB%E5%9E%8B.svg#{height="50%";width="50%";})
<p align="center">表1 中小学作文病句类型识别赛道病句类型</p>

## 2.2 赛道2：中小学作文病句改写

- 任务描述：

&emsp;&emsp;中小学作文病句改写任务是为中小学生作文中出现的错误句子，在保持语义不变的前提下，提供最小化修改方案。以往的工作只是对错误句子类型进行判断，作者只能获取到哪条句子出现了哪种错误，并不知道该如何修改，尤其对于中小学生，本身写作水平有限，写作知识的匮乏，可能并不能从错误句子类型入手自己做出正确的修改。因此，对错误句子进行自动修正对作者了解写作问题、提升写作水平具有重要意义，同时能大大节省教师评改作文时间，提高教师作文批改效率。由于语言的多样性和复杂性，错误句子修改标注本身也是一个比较费时费力的工作，考虑到大规模预训练语言模型的强大效果，所以我们希望获取针对错误句子的多样化修改方案。

- 任务定义：

&emsp;&emsp;中小学作文病句改写任务是一个文本生成任务，输入错误句子，输出修改后的句子。

## 2.3 赛道3：中小学作文流畅性评级

- 任务描述：

&emsp;&emsp;在传统的教学环境中，教师批改学生作文通常是一项耗时且繁琐的工作。教师需要通读每篇文章，综合考虑内容、结构、连贯流畅等多个方面，才能给出一个公正的等级或分数。这不仅使教师批改负担大，而且容易存在评分的主观性和不一致性。为了方便教师进行最终评分，减轻教师批改作文的负担，本次评测任务对作文流畅程度进行评级，为教师提供一个更加高效和直观的方式来评估学生的写作能力，同时也使学生能够更清晰地了解自己在写作上的表现。

- 任务定义：

&emsp;&emsp;中小学作文流畅性评级任务是一个多分类任务，输入一篇作文，输出该作文在流畅性方面的等级。本次评测任务共定义了三个流畅性等级：优秀、良好、一般。

# 3 评测数据

&emsp;&emsp;测试集中可能包含正确句子，测试数据选取子集进行评测；允许参赛者使用其他来源数据进行训练，如人工标注、使用模型或工具自动标注等，也允许借助大语言模型（如ChatGPT等）。如有使用请在技术报告中详细说明。数据仅用于当前比赛，不可挪作他用。各赛道的评测数据样例及分布如下。

## 3.1 赛道1：中小学作文病句类型识别

- **数据样例**

```json
{
    "sent_id":"3205",
    "sent":"走进那里仿佛爱丽丝梦游仙境，传统的旋转木马全换了形态各异的大鸟，旁边的转车也变成了狮子和老虎追逐，大家是不是也想来坐一坐呢。",
    "CourseGrainedErrorType":["字符级错误","成分残缺型错误"],
    "FineGrainedErrorType":["错用标点","谓语残缺"]
}
```

<p align="center">图1 中小学作文病句类型识别赛道数据样例</p>

&emsp;&emsp;图1为赛道1的数据样例，具体包括句子ID、句子序列、粗粒度错误类别、细粒度错误类别，编码格式为UTF-8。

- **评测数据集**

&emsp;&emsp;该赛道的数据来源于中学生作文数据，各项数据分布如表3所示，其中实际发放的测试集规模约7000句，选其中2000句用于评估各参赛队伍的模型效果。

<div align="center">

| 数据集（Data Set） | 句子数（sentences） |
|:---:|:---:|
| 训练集（Train Set） | 约1000句 |
| 验证集（Dev Set） | 约100句 |
| 测试集（Test Set） | 约2000句 |


</div>

<p align="center">表2 中小学作文病句类型识别赛道数据分布</p>


## 3.2 赛道2：中小学作文病句改写

- **数据样例**

```json
{
    "sent_id":"3202",
    "sent":"上周五，我就在学校用刀切破了同学的手，原因全怪我毛手毛脚，大大咧咧，用刀太快。",
    "revisedSent":"上周五，我就在学校用刀切破了同学的手，全怪我毛手毛脚，大大咧咧，用刀太快。"
}
```

<p align="center">图2 中小学作文病句改写赛道数据样例</p>

&emsp;&emsp;图2为赛道2的数据样例，具体包括句子ID、句子序列、修改后的句子，编码格式为UTF-8。


- **评测数据集**

&emsp;&emsp;该赛道的数据来源于中小学生作文数据，各项数据分布如表5所示，其中实际发放的测试集规模约7000句，选其中2000句用于评估各参赛队伍的模型效果。

<div align="center">

| 数据集（Data Set） | 句子数（sentences） |
|:---:|:---:|
| 训练集（Train Set） | 约1000句 |
| 验证集（Dev Set） | 约100句 |
| 测试集（Test Set） | 约2000句 |
</div>
<p align="center">表3 中小学作文病句改写赛道数据分布</p>


在计算最终成绩时将综合考虑三个track的分数，对于没有参加某个track的队伍，将按照该track的baseline分数进行加权，从而计算总分数。










