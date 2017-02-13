# EasyResume

EasyResume简单的使用一个json文件，配置属于你的简历的内容，只需要快捷的几步，便能生成一个样式美观整齐的在线简历。（支持移动端显示）

------------
##Demo

[查看demo](http://jaskey.github.io/easyresume "例子")

[在线编辑器(部分功能)](http://jaskey.github.io/easyresume/edit.html "在线编辑")

--------------
##快速开始

1. fork 项目
2. 为项目开启github page
3. 克隆fork后在个人名下的项目：`git clone https://github.com/YourGithubName/easyresume.git`
4. 修改`resume.json`文件，里面是简历的内容。可使用[在线编辑器(部分功能)](http://jaskey.github.io/easyresume/edit.html "在线编辑")在线编辑简单的模版后，再手动调整。
5. 提交代码并推上仓库

推仓库命令示意：
   
    git add resume.json
    git commit -m "resume init"
    git push origin 


## 在线访问： 

访问仓库的github page即可：https://yourgithubName.github.io/easyresume


## 本地预览

在推仓库前若想本地预览，需要一个布HTTP服务器，在HTTP服务下查看index.html，使用python可以简单地使用：


    python -m SimpleHTTPServer

启动一个HTTP服务，然后在[http://localhost:8000](http://localhost:8000)下查看`index.html`

-----------------------------------------------------------


# 开发者文档

整个简历仅需要读取`resume.json`文件，通过修改resume.json文件即可更新简历内容。

建议使用[在线编辑器(部分功能)](http://jaskey.github.io/easyresume/edit.html "在线编辑")在线编辑简单的模版后，再手动调整。

### resume.json键值说明

key | 说明 | 类型 | 默认
------------- | -------------| -------------| -----------
name | 姓名 | 字符串 | null
birth | 生日 | 字符串 | null
tel| 电话 | 字符串 | null
email|邮箱 | 字符串 | null
blog|博客地址 | 字符串 | null
avatar|头像地址 | 字符串 | "/image/avatar.jpg"
pages|个人主页链接 | 数组 | []
summaries|个人概况 | 字符串数组 | []
workExperiences| 工作经历| 字符串 | []
projectExperiences| 项目 | 字符串 | []
sections|其他需要额外添加的经历/段落 | 数组 | []
educations|教育经历 | 数组 | []


###工作经历

key: `workExperiences`

配置是一个对象数组，对象配置如下：

key | 说明 | 类型 | 是否可空
------------- | -------------| ------------ | -----------
company | 公司名 | 字符串 | NO
post| 所任职位 | 字符串  | NO
startDate|就职日期 | 字符串 | NO
endDate|就职结束日期 | 字符串 | NO
summary|概览 | 字符串 | YES | YES
details|经历详情|数组 | YES


###项目经历

key: `projectExperiences`

配置是一个对象数组，对象配置如下：

key | 说明 | 类型 | 是否可空
------------- | -------------| ------------ | ------------
projectName | 项目名称 | 字符串 | NO
role| 担任角色 | 字符串  | YES
startDate|项目开始日期 | 字符串 | NO
endDate|项目结束日期 | 字符串 | NO
summary|概览 | 字符串 | YES | YES
details|项目详情| 字符串数组 | YES

###教育经历

key: `educations`

配置是一个对象数组，对象配置如下：

key | 说明 | 类型 | 是否可空
------------- | -------------| ------------ | -------------
university | 学校名 | 字符串 | NO
studyType| 学历 | 字符串  | NO
major| 专业 | 字符串  | NO
startDate|项目开始日期 | 字符串 | NO
endDate|项目结束日期 | 字符串 | NO
gpa|绩点 | 字符串 | YES
scholarships|奖学金 | 字符串数组 | YES | YES
experiences|校园经历详情|字符串数组 | YES


###个人主页配置

key: `pages`

配置例子：

       		"pages":[
				{"zhihu":"http://www.zhihu.com/people/linjunjie1103"},
				{"stackoverflow":"http://stackoverflow.com/users/2087628/jaskey"},
				{"github":"https://github.com/Jaskey"},
				{"linkedin":"http://www.linkedin.com/in/jaskeylam/zh-cn?locale=zh_CN&trk=profile_view_lang_sel_click"},
				{"douban":"http://www.douban.com/people/linjunjie1103/"}
			]

对象中每个key代表一个主页类型，value是对应的链接。

key将用于渲染对应的图标，目前支持的图标有：

key | 主页
-------|-----------
stackoverflow| StackOverflow
zhihu| 知乎
github| Github
linkedin| 领英
douban| 豆瓣
segmentfault| SegmentFault
wechat| 微信
lofter| Lofter
weibo| 新浪微博

## 打赏一块几毛

如果EasyResume帮助到你找工作了，打赏几毛呗。支付宝帐号：120681430@qq.com

## License
Available under [the MIT license](http://mths.be/mit).
