pasta配置文件文档
==================
文件存储为.datacfg，按照json格式写

文件内容格式如下：

issued_data
-----------
跑数据需求的日期，比如可以写成：datatime.datatime.now()

client
-------
填入提出数据需求的产品经理，比如可以写成：yaqi

items
-----
数据需求项，现已实现的数据需求组件包括PV，UV，漏斗和计算比率四项

1、PV
^^^^^

  action:PV

  haveGroup:True or False; if True, 添加PVSetting

  PVSetting:dict; {"groupBy":group的条件}

  config: dict; 包含各配置项

     "eventKey":必填项

     "severTime":如果数据需求中有时间要求则填写

     还可以添加比如：os、appVersion等条件

  cachedata:True or False，作用忘了

2、UV
^^^^^

  action:UV

  userType:user or device

  config:
    同PV

3、funnel: 漏斗
^^^^^^^^^^^^^
  action:funnel

  sequence:漏斗的eventKey序列,列表

  haveStepConfig:True or False; if True, 添加funnelSettings

  haveParent:True or False; if True, funnelSettings中添加parents

  haveRatio:True or False

  funnelSettings:

    stepConfig:dict; sequence中需要设置的各步

    parents:dict; 用于有分支的漏斗

  filter: list,由dicts组成; 对特殊要求进行筛选, 比如付费课程等
   
     每一个筛选条件中包含: 

     type:course or user

     apply:将筛选跳进添加到stepConfig

4、ratio:计算比率
^^^^^^^^^^^^^^^^
  numerator: dict; 分子
   action:PV or UV
   config: 同上边的PV

  denominator: 分母
   同numerator
















