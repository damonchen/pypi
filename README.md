pypi
====


-------
准备工作
-------

复制.pypirc到~/.pypirc目录下，在windows下一般为C:/User/登陆用户名/


------
运行
------

切换到pypi目录下

`cd pypi/sites`
`python manage.py syncdb`
`python manage.py migrate`
`python manage.py runserver`


打开`http://localhost:8000/`

下面的文档都以`http://localhost:8000/`为例

就可以看到pypi运行


-----
注册
-----

可以通过pip命令进行安装

在注册之前，**必须要将.pypirc文件的local中的user和password修改为你在django后台中创建的用户名与密码**

如果你修改了端口号，则也必须修改.pypirc中的repository部分的端口号，总之，要使得.pypirc中的local与你搭建的后台要保持一致


切换到一个包的目录下

python setup.py register -r local sdist upload -r local

djangopypi还在mangae.py中注册了一个命令`ppadd`

python manage.py ppadd --owner yourname package_name_or_package_path

参考
http://pypi.python.org/pypi/djangopypi/0.4.4

------------
从本地安装包
------------

对于pip，采用

`pip install --index-url http://localhos:8000/simple/ django`





