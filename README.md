# win10myweb
win10如何搭建 codex环境

第一步xampp下载

https://sourceforge.net/projects/xampp/files/
启动 mysql、apache

访问测试

http://localhost

phpmyadmin测试
http://localhost/phpmyadmin/


新建网页测试
C:\xampp\htdocs\test\index.php
<?php
phpinfo();
?>

访问测试
http://localhost/test/


数据库设置密码
户账户 → root → 修改权限 → 修改密码
设置密码后，还要修改 phpMyAdmin 配置：
C:\xampp\phpMyAdmin\config.inc.php

将
$cfg['Servers'][$i]['auth_type'] = 'config';
$cfg['Servers'][$i]['user'] = 'root';
$cfg['Servers'][$i]['password'] = '';

改为
$cfg['Servers'][$i]['auth_type'] = 'cookie';


十、配置虚拟主机
C:\xampp\htdocs\myweb
C:\xampp\apache\conf\httpd.conf

Include conf/extra/httpd-vhosts.conf

打开
C:\xampp\apache\conf\extra\httpd-vhosts.conf


添加内容
<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs/myweb"
    ServerName myweb.test

    <Directory "C:/xampp/htdocs/myweb">
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>

修改
C:\Windows\System32\drivers\etc\hosts


127.0.0.1 myweb.test

http://myweb.test/



XAMPP 常用路径速查
网站目录：
C:\xampp\htdocs

Apache 配置：
C:\xampp\apache\conf\httpd.conf

Apache 虚拟主机配置：
C:\xampp\apache\conf\extra\httpd-vhosts.conf

PHP 配置：
C:\xampp\php\php.ini

MySQL/MariaDB 配置：
C:\xampp\mysql\bin\my.ini

phpMyAdmin 配置：
C:\xampp\phpMyAdmin\config.inc.php

Apache 日志：
C:\xampp\apache\logs

MySQL 数据目录：
C:\xampp\mysql\data

我的本地环境是 windows10 + xampp
配置好了apahce、mysql 环境，php可以正常访问
访问地址是  http://myweb.test
数据库用户名：root
数据库密码：123qweasd


请帮我开发一个简单美观的 PHP 任务管理系统。
功能要求：
1. 创建 myweb 数据库和 tasks 任务表
2. 页面包括添加任务功能
3. 添加任务字段包括： 任务名称、 任务说明、 任务分类、完成时间
4. 提供任务列表页面
5. 任务列表支持：
   - 按任务名称查询
   - 按完成时间范围查询
6. 每条任务可以标记完成
7. 每条任务可以删除
8. 页面要简洁、美观，适合新手学习



学习 PHP 基础，学习变量、数组、函数和表单提交，学习，2026-05-26 18:00:00
完成任务管理页面，编写任务添加、查询、完成和删除功能，开发，2026-05-27 20:00:00
