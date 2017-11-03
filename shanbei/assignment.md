若有以下9条 path和view规则：  

pattern | 说明 | view
----|----|----
/api/book/description/[a-z]+/[0-9]+ | id为一串数字的某种类别书籍的简介 | Book.All.Description
/api/book/history/[0-9]+ | id为一串数字的历史书的内容 | Book.History.Content
/api/book/comics/[0-9]+ | id为一串数字的漫画书的内容 | Book.Comics.Content
/api/book/[a-z]+/[0-9]+ | id为一串数字的某种类别书籍的内容 | Book.All.Content
/api/user/teacher/[a-z]+| id为一串字母的老师信息 | User.Teacher.Infos
/api/user/student/[a-z]+| id为一串字母的学生信息 | User.Student.Infos
/api/user/[a-z]+ | id为一串字母的用户信息 | User.All.Infos
/source/img/[0-9a-zA-Z]+| 某id的图片资源 | Source.Image
/source/scripts/[0-9a-zA-Z]+| 某id的脚本资源 |Source.Scripts

请编写算法，按照特殊大于一般的匹配原则，将所有可以匹配到上述pattern的path映射到相应的view上面，如：

path | view
----|----
/api/book/description/history/120 | Book.All.Description
/api/book/comics/123 | Book.Comics.Content
/api/user/clkjaslf | User.All.Infos
/source/img/6bq8H7q | Source.Image


###注：
1、path至view规则和一些验证相关信息在`constant.py`文件中。

2、请将代码写在`core.py`文件中。

3、`python3 core.py`运行时，可以将`paths.txt`的匹配结果逐行写入到同目录的`views.txt`中。

4、若有m条path规则，n条待计算的url，分析并给出你算法的时间复杂度。
