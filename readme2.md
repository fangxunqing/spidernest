通用化半可视化的统一的结构化爬虫环境，用户可以制作并分享爬虫，也可以从市场中或包中导入别人制作好的爬虫，并可以在其基础上进一步修改。流程化、插件化的工作方式。最后，你想要完成特定任务，只要组合特定的模块就行了。既有深度的开发灵活性，有在高层面聚合模块化组合复用的轻松之处。

面向用户：前端工程师、爬虫工程师、初级程序员（有一定的js代码能力），能够轻松制作爬虫。普通懂点技术的人，能够从市场中找爬虫，并运行爬虫。


# 基础

先以公司的任务为主，以爬取新浪的视频为一个基础任务。

云端市场，可以按Module层面查找，也可以按task(module的集合)来查找。参考npm或者pipy，用户要先注册一个账号，然后再上传，上传时在客户端登录获取auth后就能上传了。非作者无法覆盖。

两级目录，任务(task)，模块（module），一个任务由多个模块组成。可以从市场或者其他任务中导入或复制模块进来。模块有说明书(note)，方便开发者记录该模块的输入输出定义。

任务的内容，uuid作为全宇宙统一的id，然后有个可读的名字。任务的描述信息，作者，更新时间，链接(url，可以只想github等)。任务具有版本。
uuid, name, desc,doc, url, version, config, state, extra, head, middle, tail, data

模块的内容，uuid作为全宇宙统一的id，然后有个可读的名字。模块具有版本。

id, solution_id, name, doc, config, codeout, codein, extra, count, state, data

模块的运行，显示名字+id，能够显示外部Log和内部client message。

任务改成“方案”solution



关于版本管理
不做语义化的版本管理，仅做简单的整数递增的版本号管理。因为减少用户和平台的复杂度，秉承“即时可用，自查修复”。

## 关于模块之间接口的定义的问题
如果有一个固定的定义，使得能够pipe，那么模块就不需要编辑，只要链接就可以搞定任务了。
不然虽然内在业务时不需要改的，但是i/o部分需要改。

模块向外发送消息时，需要制定向谁发送。也有一些，异常消息，系统消息(开始、暂停等等)是可以广播的。也可以是指向某个模块的消息。这个很容易做。GUI的链接在一起，或者输入配置的，都可以。

消息的内容，想不到好的办法，似乎是无解的，无法把它规范化。

因而，真正的模块直接拼装是无法完成的。因而，还是以任务为市场上上传的单位。


# 测试任务：

爬取新浪新闻的视频

爬取煎蛋的图片

爬取知乎专栏的文章

爬取公众号文章

