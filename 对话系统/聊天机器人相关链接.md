# DeepLearning
聊天机器人实现的技术途径大约可分为以下4种：
（其中第一种是属于“调用第三方API”，也就是说核心代码和数据库不掌握在自己手里）（第二、三、四种属于开源框架，也就是说我们可以下载其源码，采用，相对快速的自己搭建一个聊天机器人，核心代码和数据库都掌握在自己手里）
http://homepage.fudan.edu.cn/zhengxq/deeplearning/



一、调用第三方API实现的聊天机器人 （仅以作为技术对比参考）
1.图灵机器人
https://baike.baidu.com/item/%E5%9B%BE%E7%81%B5%E6%9C%BA%E5%99%A8%E4%BA%BA/18145183?fr=aladdin
http://www.tuling123.com/products/pro_turing_robot.jhtml?nav=prod


2.api.ai
    网址：https://api.ai/
    机构/作者：Google
    流行程度：24,600,000
    简介：Google收购的一家AI公司，和wit.ai类似。提供了一个AI的框架，可以自己定义模板，参数，多轮对话，很方便的就可以定义一个自己的特定任务的聊天机器人。
https://www.leiphone.com/news/201608/u9IUSwabPaPZvD5r.html


3.Messenger Platform
    网址：https://developers.facebook.com/docs/messenger-platform
    机构/作者：Facebook
    流行程度：22,700,000
    简介：和Micros Bot Framework 是同类东西。他可以方便用户配置自己的机器人。例如某用户在网络上卖自己的商品，如果咨询太多的话，需要很多客服人员，它可以方便的配置一个客服机器人。



4.
http://www.cleverscript.com/about/



二、基于AIML技术实现的聊天机器人 (即手工编辑对话库规则：当问题中出现什么关键词----类似正则表达式----，则回答哪句预置答案)

1.AIML （Artificial Intelligence Markup Language）基础
    网址：http://www.alicebot.org/
    机构/作者：Dr. Richard S. Wallace
    流行程度：283,000
    简介：这是一个自定义的AI语言，是XML语言的扩展，支持语言规约，开源了解析器，支持主流的所有编程语言。

http://geek.csdn.net/news/detail/107645?locationNum=11&fps=1


2.python aiml
https://www.dssz.com/2829799.html
https://www.zhihu.com/question/19651613
https://www.urlteam.org/2016/01/python-aiml%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD%EF%BC%8B%E7%99%BE%E5%BA%A6%E8%AF%AD%E9%9F%B3%E5%AF%B9%E8%AF%9D/
http://blog.csdn.net/golearn/article/details/50373580
http://blog.csdn.net/tobacco5648/article/details/50595396
https://www.biaodianfu.com/python-aiml.html
http://python.jobbole.com/82007/
https://pypi.python.org/pypi/python-aiml/0.9.0
https://yq.aliyun.com/ziliao/25421
https://www.jianshu.com/p/d6230f63402a
http://www.jb51.net/article/78789.htm


3.AIML
http://study.163.com/course/courseLearn.htm?courseId=1005049028#/learn/video?lessonId=1051673662&courseId=1005049028 


4.Rasa Core
https://blog.csdn.net/love_is_red/article/details/79145979


5.AIML
https://blog.csdn.net/wxlfight/article/details/8093792


6.AliceBot
https://blog.csdn.net/a_piaoyouareminemine/article/details/50151599
https://my.oschina.net/dancing/blog/161700



三、基于机器学习的聊天机器人 （重点）
1.python chatterbot
第3课-机器学习构建聊天机器人
ChatterBot
    网址：https://github.com/gunthercox/ChatterBot
    机构/作者：Gunther Cox
    流行程度：206,000
    简介：这是一个闲聊系统，Python语言，基于检索方式，不适用于基于任务的对话系统。
https://blog.csdn.net/hfutdog/article/details/78155467




四、任务式聊天机器人 （AIML+外部系统功能/API调用） （采用opendial，重点）
1.http://study.163.com/course/courseLearn.htm?courseId=1005049028#/learn/video?lessonId=1051673662&courseId=1005049028
2.  opendial 
    网址：http://www.opendial-toolkit.net/
    机构/作者：Lison, P.
    流行程度：147,000
    简介：有较好的澄清机制，基于规则的系统，没有太多的机器学习和深度学习技术，在参数调节部分用到了机器学习技术。





五、多轮对话（即上下文记忆）聊天机器人（即  记住用户上句话和上上句话）（状态标志器变量+AIML） （采用opendial，重点）
1.http://study.163.com/course/courseLearn.htm?courseId=1005049028#/learn/video?lessonId=1051673662&courseId=1005049028

2.https://www.douban.com/note/635914266/?from=tag




六、基于深度学习的聊天机器人 （重点）
1.一位大神的framework，具体而详尽
https://github.com/qhduan/Seq2Seq_Chatbot_QA
https://github.com/qhduan/just_another_seq2seq

2.另一位牛人的工作
http://www.shareditor.com/blogshow?blogId=121


3.deepQA2等十个框架 （仅简介、需详细了解和斟酌）（我这边先调研一下）
https://github.com/fateleak/awesome-chatbot-list


4.《06-自动聊天机器人项目班》中“深度学习聊天机器人”部分（视频课程+代码，可直接部署）


5.《06-自动聊天机器人项目班》中“VQA”部分（视频课程+代码，可直接部署）

6.deepQA2
https://blog.csdn.net/u013378306/article/details/55213619
https://www.leiphone.com/news/201702/4OZau7OfcNO0v1u5.html
https://www.v2ex.com/t/388328
https://github.com/Conchylicultor/DeepQA
http://news.163.com/16/0325/17/BJ14NPAA000146BE.html


7.tensorflow chatbot
https://blog.csdn.net/hfutdog/article/details/78155467


8.（another）seq2seq
http://36kr.com/p/5089608.html


9.FudanDNN-NLP4.0
http://homepage.fudan.edu.cn/zhengxq/deeplearning/



七、基于信息检索的聊天机器人
1.AIML+FUSEKI知识库系统
http://study.163.com/course/courseLearn.htm?courseId=1005049028#/learn/video?lessonId=1051673662&courseId=1005049028


2.Lucene
http://www.shareditor.com/blogshow?blogId=113


3.MITIE+AliceBot+DB
https://blog.csdn.net/wangyangzhizhou/article/details/79245144

4.AIML=DB
https://blog.csdn.net/wxlfight/article/details/8093792







八、API、wx+chatbot
《聊天机器人技术概述.doc》


利用Tornado可以很方便地搭建一个web接口的聊天机器人。具体的代码可以在此链接下在：web接口的聊天机器人。 
下载此代码之后直接运行main.py即可，然后可以通过浏览器访问url与聊天机器人，url类似http://localhost/aiml?req=hello的形式（req参数即为发给机器人的信息）。 
注意要运行此代码，需要安装Python 的aiml与Tornado库。 
lwons.com上已经搭建了这样的web接口，可以访问http://lwons.com/aiml?req=hello来测试下。
https://blog.csdn.net/tobacco5648/article/details/50595396




九、BAT和其他大公司自己用的不开源的聊天机器人(别人不能调用API、也不能下载源码框架)（因此不用特别关注）
1.度秘

2. wit.ai
    网址：https://wit.ai
    机构/作者：Facebook
    流行程度：351,000,000
    简介：是所有框架中最流程的一个，有非常好的二次开放库，duckling.wit.ai是非常好的时间识别库。wit.ai并不开源的，但是二次库很多事开源的，详见github上面的二次开发库。


3.Language Understanding Intelligent Service (LUIS)
    网址：https://www.luis.ai/
    机构/作者：Microsoft
    流行程度：8,020,000
    简介：和wit.ai，api.ai类似，是微软在这方面的一个产品。

4.Microsoft Bot Framework
    网址：https://dev.botframework.com/
    机构/作者：Microsoft
    流行程度：532,000
    简介：这是一个应用层的框架，里面用到的技术是luis.ai和微软的其他人工智能技术。


5. viv 
    网址：http://viv.ai/
    机构/作者：Siri之父，三星收购
    流行程度：61,200,000
    简介：准确来说，其不算是一个框架，没有开源，也还没有产品出来。据其作者宣城，其特点是，采用了计算机动态自动编程技术，不用再硬编码了。








十、参考资料

这个网址中列出了一些聊天机器人（各种技术路线的都有）
http://blog.csdn.net/xmsheji/article/details/53610656
这个网址中列出了很多深度学习的聊天机器人
https://github.com/fateleak/awesome-chatbot-list



注： 其中study.163.com上的课程已买，远程登录即可。




十一、增量训练  （俗称tiaoj）
https://baike.baidu.com/item/%E5%A4%A9%E6%89%8D%E7%90%AA%E9%9C%B2%E8%AF%BA/4161424?fr=aladdin
http://www.cleverbot.com/




十二、进阶
https://www.zhihu.com/question/20060159
