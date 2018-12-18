
[toc]


### Django 项目操作

##### 1、创建多个app

>django是MTV模式，即template（页面展现），modle（数据库表对象）,view（业务逻辑处理），在开发中发现，随着项目功能的增多，把所有的功能模块放在一个app肯定不切实际，也不符合网站开发的原则。

**语法：python manage.py startapp rbac （appname）**


![Alt text](./屏幕快照 2018-12-12 下午1.38.07.png)

#####2、 在setting里面手动添加app
![Alt text](./屏幕快照 2018-12-16 下午12.21.31.png)


##### 3、数据库配置
    
	终端 mysql -uroot -p   进入私人操作，无密码，点击回车
	create database db_crm charset utf8;

	settings.py 设置替代原有的
	DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME':'db_bbs',
        'USER':'root',
        'PASSWORD':'',
        'HOST':'127.0.0.1',
        'PORT':''
    }
	}


![Alt text](./屏幕快照 2018-12-16 下午12.40.16.png)


![Alt text](./屏幕快照 2018-12-16 下午12.46.41.png)


##### 4、创建表并数据迁移语法
**语法：python manage.py makemigrations**
**语法：python manage.py migrate**




##### 5、静态文件配置
setting.py里面配置

    # 静态文件胚子
	STATIC_URL = '/static/'

	STATIC_DIR =   (
    os.path.join(BASE_DIR, "static"),
	)


##### 6、模板引入静态文件

    前端引入

	在页面的较上处写：
	
	{% load staticfiles %}
	
	在 link script 等src 写 ：
	
	{%static 'xxx.css'%}　
	
	{%static 'xxx.js'%}

![Alt text](./屏幕快照 2018-12-16 下午3.47.34.png)

##### 7、创建超级用户
**语法：python manage.py createsuperuser**
![Alt text](./屏幕快照 2018-12-16 下午4.20.40.png)


##### 8、后台admin注册

把rbac下的models.py里面的表注册到后台管理
![Alt text](./屏幕快照 2018-12-17 上午11.08.50.png)


#####9、inclusion_tag的用法

>可以封装一些公共区域模板代码，继承复用

在app中创建templatetags模块(模块名只能是templatetags)

模板使用前要导入  {% load rbac %}

![Alt text](./屏幕快照 2018-12-17 下午9.31.32.png)

封装的模板

![Alt text](./屏幕快照 2018-12-17 下午5.32.11.png)


##### 10、自定义中间件
>中间件顾名思义，是介于request与response处理之间的一道处理过程，相对比较轻量级，并且在全局上改变django的输入与输出。因为改变的是全局，所以需要谨慎实用，用不好会影响到性能。

自定义的中间件要继承MiddlewareMixin
![Alt text](./屏幕快照 2018-12-18 上午9.46.27.png)

注册
![Alt text](./屏幕快照 2018-12-17 下午1.19.50.png)