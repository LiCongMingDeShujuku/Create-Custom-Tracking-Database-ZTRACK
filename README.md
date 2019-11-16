![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 创建自定义跟踪数据库ZTRACK
#### Create Custom Tracking Database ZTRACK
**发布-日期: 2015年11月20日 (评论)**

![#](images/image0012.png?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
ZTRACK数据库是我写的一个不包含任何其他数据库服务或相关的SQL功能的简单的小型跟踪解决方案。基本上这是一个只使用一系列代理作业，查询和触发器进行管理的自定义数据库。如果你是那种喜欢编写自己的解决方案的
数据库管理员（DBA），因为它快速，可靠，并且不需要付出很多努力，那么这就适合你。所有内容都包含在ZTRACK数据库中，因此你创建的任何对象（除了主要存在于系统表上的触发器之外）都应保存在此数据库中。
下面我们开始。 第一，创建一个名为ZTRACK的数据库。没有花哨的东西。使用所有默认值，然后运行以下逻辑（logic）来创建表格。ZTRACK数据库的第一个表格叫做ABOUT_ZTRACK。它给所有你创建的内容一个基本的
描述。我在表名前加上“zt”，以避免与已存在的关键字发生任何名称冲突。 这可能会使查询变得更容易些。



## English
The ZTRACK database is my simple little tracking solution without having to incorporate any other database services, or associated SQL Features. Basically this is a custom Database that’s managed with just a series of , queries, triggers. If you’re the kind of DBA that likes to write up your own kind of solution cause it’s fast, reliable, and doesn’t require a lot of effort then this is for you. Everything is contained without the ZTRACK Database so any objects you create (aside from triggers which mainly reside on the system tables), should be kept in this database.
Lets begin. First; create a database called ZTRACK. Nothing fancy. Use all the defaults, then run the following logic to create the tables. The first table of the ZTRACK database is called ABOUT_ZTRACK. This gives a basic description for everything you create. I’m prefixing the table names with “zt” as to avoid any name collision with reserved keywords. This might make queries alittle easier.


---
## Logic
```SQL
use ZTRACK;
set nocount on
 
create table ABOUT_ZTRACK
(
zt_id int identity(1,1) primary key not null
,   zt_object_type varchar(255)
,   zt_object_name varchar(255)
,   zt_object_logic varchar(max) default 'None'
,   zt_description varchar(max)
)
 
insert into about_ztrack
(
zt_object_type
,   zt_object_name
--, zt_object_logic
,   zt_description
)
values
(
'DATABASE'
,   'ZTRACK'
--,
,   'This Database is desiged to hold information about various system configurations, growth history, and performance history.' )
此数据库旨在保存有关各种系统配置，增长历史记录和性能历史记录的信息


```

你可以创建一个条目并给它一个描述，或者在SYSOBJECTS表格下创建一个触发器，并自动创建一个条目;，然后可以在必要时更新zt_description列。

It’s up to you to commit to creating a an entry and give it a description… Or… create a triggers under the SYSOBJECTS table, and create an entry automatically; then you can simply update the zt_description column later on if necessary.



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

