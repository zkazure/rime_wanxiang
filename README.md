## Wishlist 
- [ ] pure edition
- [ ] make dual input method 
- [ ] add 自然龙 to the website to practice. [website](https://github.com/BlueSky-07/Shuang)

## 自然龙
### 单
#### a
拉啥马差
#### e
rr鹅ll彻
#### i
积鼻替gg
#### o
坡eeiigg
#### u
aa卢母户
#### v
hhmmssff

### 2


### 3


### 4
#### iang
yyiiuuee
#### uang
wwbb爽ee
#### iong
ppkkeehh

### Code
![code-1](./images/code-1.jpg)
![code-2](./images/code-2.jpg)
![code-3](./images/code-3.jpg)
![code-4](./images/code-4.jpg)

## Other

**配套方案** 本方案为万象系列方案基础版    [>>辅助码增强版本](https://github.com/amzxyz/rime_wanxiang_pro)  

 [为什么默认关闭调频的说明](https://github.com/amzxyz/RIME-LMDG/wiki/%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E5%85%B3%E9%97%AD%E8%B0%83%E9%A2%91%E4%BB%A5%E5%8F%8A%E4%B8%8E%E4%B9%8B%E5%85%B3%E8%81%94%E7%9A%84%E6%8E%AA%E6%96%BD%E6%9C%89%E5%93%AA%E4%BA%9B)    ```enable_user_dict: false # 是否开启自动调频，true为开启```

 这里推荐使用`(1左侧的按键)引导的精准造词，万象默认关闭主翻译器用户词功能，开放次翻译器用户词功能，如果你的输入出现了次选，那么次选可以直接进用户词库，词库文件zc.userdb.txt

**基于[万象词库](https://github.com/amzxyz/RIME-LMDG)以及语法模型的基础上修改而来，是一个集成了带调词库、预测模型的基础全拼双拼方案，在这套词库作为底座支撑之下，传统双拼轻松支持、自然龙、龙码等带调方案亦可轻松支持，因此同样是一个集合多种拼音方案的集合，让你不用迁移配置即可轻松切换方案。**

**万象词库中的带声调拼音标注+词组构成+词频是整个万象项目的核心，是使用体验的基石，方案的其它功能皆可自定义，我希望使用者可以基于词库+转写的方式获得输入体验** [万象词库问题收集反馈表](https://docs.qq.com/smartsheet/DWHZsdnZZaGh5bWJI?viewId=vUQPXH&tab=BB08J2)

**由于词库是全局携带声调的，因此这里侧重推荐进阶用户使用：[自然龙](https://github.com/rimeinn/rime-zrlong) 方案，这是一种韵母带声调的双拼输入方式，万象已经内置自然龙运算方案，表头即可配置**

---
效果大赏

![效果.png](https://storage.deepin.org/thread/202502200358104987_效果.png)

---

**1. 如何使用：**

 首先

打开万象项目主方案 ```wanxiang.schema.yaml```，编辑表头，选择方案, 需要注意在手机上使用同文输入法时，长按回车键进入功能菜单选中与方案匹配的布局

```
#############万象拼音无辅助码版本###########################
set_shuru_schema:         #配置此项就是选择什么输入法,同时拆分反查和中英文混输也将匹配该输入方案
  __include: 自然码  #可选解码规则有   全拼, 自然码, 自然龙, 小鹤, 搜狗, 微软  选择一个填入
set_gongjian_mohu:    #可选的值有：26键, 18键, 14键, 9键  注意PC选26键
  __include: 18键
pro_comment_format:           # 超级注释模块
  candidate_length: 1         # 候选词注释提醒的生效长度，0为关闭  但同时清空其它，应当使用开关或者快捷键来处理    
  corrector_type: "{comment}"  #错音错词提示显示类型，比如"({comment})" 
########################以下是方案配置######################################################
```

可以说非常清晰了，定义方案名称、拼音类型、以及注释显示逻辑，配置完毕保存。

继续分别打开```radical_pinyin.schema.yaml```  ```melt_eng.schema``` 分别对反查和英文解码方案进行表头配置

```
###############选择与之匹配的拼音方案#####################

set_shuru_schema:

  __include: algebra_zrm   #可选的选项有（algebra_pinyin, algebra_zrm, algebra_flypy, algebra_mspy, algebra_sogou, algebra_abc, algebra_ziguang）
```

同样选择对应的拼音类型即可，保存后即可部署使用了

**2.功能介绍：**

**日期、时间、节日、节气、问候模板：**

```
#时间：osj 或者 /sj
#日期：orq 或者 /rq
#农历：onl 或者 /nl
#星期：oxq 或者 /xq
#今年第几周：oww 或者 /ww
#节气：ojq 或者 /jq
#日期+时间：ors 或者 /rs
#时间戳：ott 或者 /tt
#大写N日期：N20250315
#节日：ojr 或者 /jr
#问候模板：/day 或者 oday
```

**Unicode：** 大写 U 开头，如 U62fc 得到「拼」。

**数字、金额大写：**  大写 R 开头，如 R1234 得到「一千二百三十四、壹仟贰佰叁拾肆元整」。

 **/模式：**  通过输入 /sx 快捷输入关于“数学”的特殊符号，具体能输入什么可以打开 symbols.yaml学习。

 **计算器：**  通过输入大写V引导继续输入如：V3+5  候选框就会有8和3+5=8，基础功能 `+ - * / % ^` 还支持 `sin(x) cos(x)` 等众多运算方式 [点击全面学习](https://github.com/gaboolic/rime-shuangpin-fuzhuma/blob/main/md/calc.md)

 **自动上屏：**  例如：三位、四位简码唯一时，自动上屏如`jjkw岌岌可危` `zmhu怎么回事` 。默认未开启，方案文件中`speller:`字段下取消注释这两句开启 `#   auto_select: true  #  auto_select_pattern: ^[a-z]+/|^[a-df-zA-DF-Z]\w{3}|^e\w{4}`

 **错音错字提示：**  例如：输入`gei yu给予`，获得`jǐ yǔ`提示

 **快符与重复上屏：** 例如 ```'q``` 通过单引号键引导的26字母快速符号自动上屏，对整个键盘符号进行补充扩展，重复上屏使用符号与汉字字母上屏的分离记忆，双击''重复上一个符号，包含直接上屏的输入符号，如shift+3输入的#号，双击;;获得上一次候选词的重复上屏，在输入汉字的时候，符号的最后一次提交是被保留的，这样例如在写作时候才能真真的有场景来使用重复上屏符号。

**超级tips：** 支持将表情、化学式、翻译、简码 提示等等你能想到得数据获得提示显示并将通过一个自定义按键直接上屏，默认为"." ，避免了占用候选框，通过Control+t 进行开关；

 **声调的使用：** 任意长度候选词的注释提示能力，默认开启1个字的长度，输入状态下：Ctrl+a开启和关闭注释候选词带声调，输入状态下：Ctrl+s开启关闭输入码带声调。

 **用户词删除：** 不管什么删除都不能直接作用于固定词典，使用Ctrl+del是rime系统删除用户词，基于lua的实现：对选中的候选词操作，使用Ctrl+d 删除，Ctrl+x隐藏，Ctrl+j降低词频，删除的词都在lua下文件中记录，你可以清空重新部署恢复，也可以根据列出去清除固定词典的编码，从而持续迭代。

 **Tab循环切换音节：**  当输入多个字词时想要给前面补充辅助码，可以多次按下tab循环切换，这种可能比那些复杂的快捷键好用一些。

 **翻译模式：**  输入状态按下Ctrl+E快捷键进入翻译模式，原理是opencc查表进行中英文互译，能否翻译取决于词表的丰富度；

 **反查：** 支持``` ` ```、``` `` ```引导状态下的显示格式化，``` ` ```是部件组字，``` `` ```是笔画组字。反查模式不受字符集过滤影响，默认开放大字集,也不受辅助码开关影响，会显示注释；

 **字符集过滤：** 默认开启过滤，写在charset.dict.yaml的就是可以通过的字表，默认为8105+𰻞𰻞，如果你想什么字在小字集模式可以通过可以写在这里，配套开关【小、大】，快捷键Ctrl+g

 **3. 词库可移植性：**

- 第一个是如果迁移到你的项目中，第1项中已有解答，或者使用单一变化 - xform/ā/a/

- 词库附带方案的使用，由于rime不可避免的人人都要修改配置，因此我将配置简化，避免多方案部署，带着疑问去使用本方案，有助于了解rime的结构。

```直接的转写：参考项目中自然龙的布局转写方式```

在原来的方案中拼写运算的首位添加一句话，就可以像以前一样使用了，无任何不同，所以可以轻松迁移
##### 无声调：

```
 algebra:
    - xlit/āáǎàōóǒòēéěèīíǐìūúǔùǖǘǚǜü/aaaaooooeeeeiiiiuuuuvvvvv/
    - xform/ń|ň|ǹ/en/ 
    - xform/ńg|ňg|ǹg/eng/
```
##### 末尾数字声调：
```
    - xform/ń/én/ 
    - xform/ň/ěn/ 
    - xform/ǹ/ěn/ 
    - xform/ńg/éng/
    - xform/ňg/ěng/
    - xform/ṅg/èng/

    - xform/^([a-zA-Z]+)$/$1⑤/
    - xform/^(.*)ā(.*)$/$1a$2①/
    - xform/^(.*)á(.*)$/$1a$2②/
    - xform/^(.*)ǎ(.*)$/$1a$2③/
    - xform/^(.*)à(.*)$/$1a$2④/

    - xform/^(.*)ō(.*)$/$1o$2①/
    - xform/^(.*)ó(.*)$/$1o$2②/
    - xform/^(.*)ǒ(.*)$/$1o$2③/
    - xform/^(.*)ò(.*)$/$1o$2④/

    - xform/^(.*)ē(.*)$/$1e$2①/
    - xform/^(.*)é(.*)$/$1e$2②/
    - xform/^(.*)ě(.*)$/$1e$2③/
    - xform/^(.*)è(.*)$/$1e$2④/

    - xform/^(.*)ī(.*)$/$1i$2①/
    - xform/^(.*)í(.*)$/$1i$2②/
    - xform/^(.*)ǐ(.*)$/$1i$2③/
    - xform/^(.*)ì(.*)$/$1i$2④/

    - xform/^(.*)ū(.*)$/$1u$2①/
    - xform/^(.*)ú(.*)$/$1u$2②/
    - xform/^(.*)ǔ(.*)$/$1u$2③/
    - xform/^(.*)ù(.*)$/$1u$2④/

    - xform/^(.*)ǖ(.*)$/$1v$2①/
    - xform/^(.*)ǘ(.*)$/$1v$2②/
    - xform/^(.*)ǚ(.*)$/$1v$2③/
    - xform/^(.*)ǜ(.*)$/$1v$2④/
    - xform/^(.*)ü(.*)$/$1v$2/
    - xlit/①②③④⑤/12345
```
##### 数字跟随元音声调：
```
    - xform/ā/a1 
    - xform/á/a2 
    - xform/ǎ/a3 
    - xform/à/a4 
    - xform/ō/o1
    - xform/ó/o2
    - xform/ǒ/o3
    - xform/ò/o4
    - xform/ē/e1 
    - xform/é/e2 
    - xform/ě/e3 
    - xform/è/e4 
    - xform/ī/i1 
    - xform/í/i2 
    - xform/ǐ/i3 
    - xform/ì/i4 
    - xform/ū/u1 
    - xform/ú/u2 
    - xform/ǔ/u3 
    - xform/ù/u4 
    - xform/ǖ/v1 
    - xform/ǘ/v2 
    - xform/ǚ/v3 
    - xform/ǜ/v4 
    - xform/ü/v1
```
**4. 同文说明**：由于同文不具备拼音筛选器，因此想要体验特别好的小于26键的输入是不现实的，而依托万象拼音强大的词频与语言模型一定程度上弥补了这种不足。为了实现9键、14键、18键这几种常用的涉及到共键的输入方式，我们需要整体对方案层面进行运算处理，对同文主题进行深度定制，共同配合之下才能实现共键输入，下面我从几个方面阐述和说明。

**定制原理：** 

1. 对同文输入法皮肤进行定制，实现共键单发，例如WE共键，按下只发送w；
2. 对方案拼写运算进行结构化处理，将共键字母中例如WE中的e转换为w，多个字母同样处理；
3. 配合定制键盘即可打字。
   

**注意事项：**
1. 使用低于26键时，可以注释掉开关中的中英文切换，使用键盘来切换，避免逻辑冲突；
2. 使用低于26键时，中英文混输、反查基本上是废了，因为无法精准输出单键字母；
3. 使用低于26键时，由于实现方法不同于大厂，严格考虑能否接受口水聊天级别的轻量化使用，有更高追求的直接使用26健
4. 使用低于26键时，修改键盘布局要修改wanxiang方案表头部分，和同文键盘同时切换（长按回车键弹出功能菜单选择对应布局）才能正常使用
   

<img src="https://storage.deepin.org/thread/202409250204031318_26.jpg" width="400">             <img src="https://storage.deepin.org/thread/202409250204112540_18.jpg" width="400">   
<img src="https://storage.deepin.org/thread/202409250204092790_14.jpg" width="400">             <img src="https://storage.deepin.org/thread/202409250204064425_9.jpg" width="400"> 

**5. 简化配置和加载项：**

从前我们对声调的利用需要配置专门的外挂词库，形式包括：

- 外挂方案，然后挂接到主方案中，进行反查；

- 通过opencc转换器覆盖，两种坏处，一个是需要加载独立文件，另一个是覆盖性的注释不利于多态共存，比如平时显示辅助码的时候，出现单一的错词提示的时候做不到都显示和逻辑替换；

- lua脚本的需要复杂的逻辑，加载文件，解析格式深加工格式，遍历候选，提交替换结果。

 

以前做好这几件事需要多个字表、多个lua协同，配置文件里要引入多个加载器。

而现在注释本来的面目就是带着声调的，你只需要完全暴露注释，他就是显示拼音声调的形态，你可以使用lua简单的加个括号等等简易的格式操作，可以借助lua接口将其替换到输入码preedit、注释comment，在反查时由于rime本身的注释生成特性，多音字都会被一一罗列到注释里，你无需额外维护多音字字表。在用户态里的感知就是无需复杂配置，无需加载过多的文件，节约内存开销，提升性能，减少方案文件维护成本。

