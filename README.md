# IdentityServer4
目前的话，暂时只做了基于内存的授权，下次将利用EFCore把权限信息写入到数据中
## 简单介绍
简单说一下我做了那些内容：
（1）首先是建立了一个空的.net Core MVC的项目
（2）直接用脚手架命令 把ID4的 quickUI直接 Down下来，直接利用他的模板
（3）在start up中进行Id4的服务注册，中间件的配置,在InMemoryConfig类文件中配置当前的用户、客户端、以及API之间的关系；例如我这里定义叫做myvuejs的客户端， ClientId = "myvuejs",让他能访问的作用域为mycore.api，AllowedScopes = new [] { "mycore.api" }// 允许访问的 API 资源,这里将客户端和他能够访问的API资源联系起来
（4）建立一个webapi，他的名称定义为mycore.api
(5)测试：利用Postman 根据Clientid名称，用户以及密码拿到一个Token,然后拿到这个Token去请求WebApi
