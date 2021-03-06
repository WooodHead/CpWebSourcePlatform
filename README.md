# CpWebSourcePlatform

![image](https://github.com/10086XIAOZHANG/blogImgAttr/blob/master/916E727D11F718DB050BC153B6D204F9.png)
![image](https://github.com/10086XIAOZHANG/blogImgAttr/blob/master/%E6%97%A5%E5%BF%97%E7%AE%A1%E7%90%86.gif)
![image](https://github.com/10086XIAOZHANG/blogImgAttr/blob/master/%E5%90%8E%E5%8F%B0%E7%AE%A1%E7%90%86.gif)
#### 项目介绍
- 文档自动化管理 / Django REST framework的缓存
Throttling对用户和IP进行限速
-集成QQ/微信/微博第三方登录
- Authentication用户认证设置
动态设置Permission、Authentication
Validators实现字段验证
- Serializer
ModelSerializer
动态设置Serializer
- Apiview方式实现API接口 / GenericView方式实现API接口
Viewset和Router方式实现API接口和URL配置
Django_filter、SearchFilter、OrderFilter、分页 / 通用Mixins
- 使用Redis对Django REST framework常用且访问大的开放接口进行缓存加速
cp聚合博客--python后台

#### 软件架构

该平台采用Django2.0 xadmin  restframework api 开发


#### 使用说明

1. Django的版本要求必须是2.0版本,使之能和xadmin 对得上
2. GitHub 上面的xadmin 对Django的版本的选择还是存在诸多问题

#### 云之讯 其中注册会采用云之讯的短信服务

```
YUNZHIXUN_TOKEN = "****"
YUNZHIXUN_TEMPLATE_ID = "***"
```

#### 在utils/yunzhixun.py中提供func对云之讯的调用

#### mysql 配置账号密码

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': "CpWebSourcePlatform",
        'USER': 'root',
        'PASSWORD': "*******",
        'HOST': "*****",
        'OPTIONS': {'init_command': 'SET default_storage_engine=INNODB;'}
    }
}
```

#### 在urls.py 中 主要配置api 匹配规则

```
urlpatterns = [
    # authentication / association
    url(r'^login/(?P<backend>[^/]+){0}$'.format(extra), views.auth,
        name='begin'),
    url(r'^complete/(?P<backend>[^/]+){0}$'.format(extra), views.complete,
        name='complete'),
    # disconnection
    url(r'^disconnect/(?P<backend>[^/]+){0}$'.format(extra), views.disconnect,
        name='disconnect'),
    url(r'^disconnect/(?P<backend>[^/]+)/(?P<association_id>\d+){0}$'
        .format(extra), views.disconnect, name='disconnect_individual'),
]
```

#### 通过social_django为项目提供第三方的分享

### CP聚合博客Web端-基于react+dva2+andsign+react-router4.0框架——https://github.com/10086XIAOZHANG/CP-WEB-SOURCE-PlATFORM
### CP聚合博客移动端——基于React Native支持Android和iOS双平台移动端APP: https://github.com/10086XIAOZHANG/CpBlogApp/tree/master
### 博客地址：[https://www.cnblogs.com/fuGuy/](https://www.cnblogs.com/fuGuy/)
