# Web

RESTful API Requirements
====
http://www.ruanyifeng.com/blog/2018/10/restful-api-best-practices.html

RESTful 是目前最流行的 API 设计规范，用于 Web 数据接口的设计。
它的大原则容易把握，但是细节不容易做对。本文总结 RESTful 的设计细节，介绍如何设计出易于理解和使用的 API。


HTTP 动词
====
https://godruoyi.com/posts/the-resetful-api-design-specification
对于资源的具体操作类型，由 HTTP 动词表示。常用的 HTTP 动词有下面五个（括号里是对应的 SQL 命令）。
其中:
删除资源 必须 用 DELETE 方法
创建新的资源 必须 使用 POST 方法
更新资源 应该 使用 PUT 方法
获取资源信息 必须 使用 GET 方法
针对每一个端点来说，下面列出所有可行的 HTTP 动词和端点的组合

请求方法	URL	描述
GET	/zoos	列出所有的动物园(ID和名称，不要太详细)
POST	/zoos	新增一个新的动物园
GET	/zoos/{zoo}	获取指定动物园详情
PUT	/zoos/{zoo}	更新指定动物园(整个对象)
PATCH	/zoos/{zoo}	更新动物园(部分对象)
DELETE	/zoos/{zoo}	删除指定动物园
GET	/zoos/{zoo}/animals	检索指定动物园下的动物列表(ID和名称，不要太详细)
GET	/animals	列出所有动物(ID和名称)。
POST	/animals	新增新的动物
GET	/animals/{animal}	获取指定的动物详情
PUT	/animals/{animal}	更新指定的动物(整个对象)
PATCH	/animals/{animal}	更新指定的动物(部分对象)
GET	/animal_types	获取所有动物类型(ID和名称，不要太详细)
GET	/animal_types/{type}	获取指定的动物类型详情
GET	/employees	检索整个雇员列表
GET	/employees/{employee}	检索指定特定的员工
GET	/zoos/{zoo}/employees	检索在这个动物园工作的雇员的名单(身份证和姓名)
POST	/employees	新增指定新员工
POST	/zoos/{zoo}/employees	在特定的动物园雇佣一名员工
DELETE	/zoos/{zoo}/employees/{employee}	从某个动物园解雇一名员工
