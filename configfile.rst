pasta配置文件文档
==================
文档存储为.datacfg 文件

文档格式如下：

issued_data
-----------
数据需求的日期，比如可以写成：datatime.datatime.now()

client
-------
填入提出数据需求的产品经理，比如：yaqi

items
-----
数据需求项，现已实现的数据需求包括PV，UV，漏斗和计算比率四项

PV:计算PV
^^^^^^^^^

action:PV

haveGroup:如果没有条件，写成False;如果有条件，就写成True，添加PVSetting

PVSetting:"groupBy":添加group的条件

config:添加各配置项
   "eventKey":必填项
   "severTime":如果数据需求中有时间要求
   还可以添加比如：os、device等字段

cachedata:填True or False，作用忘了

UV：计算UV
^^^^^^^^^

action:UV

userType:user or device

config:
   同PV

funnel:漏斗
^^^^^^^^^^^
action:funnel

sequence:漏斗的eventKey序列,列表

haveStepConfig:True or False; if True, then fill funnelSettings

haveParent:True or False

haveRatio:True or False

funnelSettings:

   stepConfig:dict; fill in every step's request

   parents:dict; parent and sub

filter:exceptional request,for example:payable courses;list,includes dicts
   
   for each in filter

   type:course or user

   apply:to the stepConfig

ratio:caculate ratio
^^^^^^^^^^^^^^^^^^^^
numerator:need to caculate;dict
   action:PV or UV
   config: like PV above

denominator:
   like numerator
















