Welcome to Beacon Notify Demo documentation!
=======================================

這份文件是 中華電信研究院 Beacon Notify 元件的 使用手冊。

最新消息
-------------
**[注意!!] 本次改版`(2.18.x)`變更了元件呼叫架構，請務必變更您原始的呼叫方式並參考使用手冊中的初始化章節**  
### Version: 2.18.06 ###
```
 1. 新增 [App][Lib] 簡訊顯示模式
 2. 新增 [App][Lib] 定位事件模式(有關事件定義及操作請參考前端編輯平台說明)
 3. 修正 [Lib] 初始呼叫元件框架架構，使呼叫元件更為彈性
 4. 修正 [Lib] 浮動泡泡顯示模式，使整個浮動泡泡更穩定、提昇效能及美化介面
 5. 更新 [Lib] 底層 SBeacon 核心元件升級為 V2.2.2
```

Get the code
-------------

The `source <http://github.com/ericholscher/django-kong>`_ is available on Github. I would like to thank `Nathan Borror <http://nathanborror.com>`_ for the design parts that are pretty :)

The mailing list for the project is located at google groups: http://groups.google.com/group/django-testing

Contents
--------

.. toctree::
   :maxdepth: 2
   :glob:

   install
   management_commands
   settings
   overview
   meta
   roadmap

What's with the name?
----------------------

Originally Kong was called paradigm, because it was going to change the way we thought about deployment. After much convincing from coworkers that this was too enterprisey, during the Djangocon 09 sprints, I was given the name Donkey Kong. I thought it would be a fun play on words to name a project django kong, because it sounds like Djangocon, and it plays off of Donkey Kong. Then I just needed to find a way to associate Kong with what the project actually does, because it's a Deployment Testing Tool for King/Donkey Kong sized sites.

