---
title: Apollo配置中心
date: 2020-5-24 23:35:54
cover: https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220524233622.png
tags:
- 组件
---
# 主流配置中心产品
1. Disconf
   2014年7月百度开源的配置管理中心，专注于各种「分布式系统配置管理」的「通用组件」和「通
   用平台」, 提供统一的「配置管理服务」。目前已经不再维护更新。
   https://github.com/knightliao/disconf
2. Spring Cloud Config
   2014年9月开源，Spring Cloud 生态组件，可以和Spring Cloud体系无缝整合。
   https://github.com/spring-cloud/spring-cloud-config
3. Apollo
   2016年5月，携程开源的配置管理中心，能够集中化管理应用不同环境、不同集群的配置，配置修
   改后能够实时推送到应用端，并且具备规范的权限、流程治理等特性，适用于微服务配置管理场
   景。
   https://github.com/ctripcorp/apollo
4. Nacos
   2018年6月，阿里开源的配置中心，也可以做DNS和RPC的服务发现。
   https://github.com/alibaba/nacos
# 产品对比
Apollo集成了数据库+Eureka+版本控制+权限管理+Http Long Polling ... ...

总的来说，Apollo和Nacos相对于Spring Cloud Config的生态支持更广，在配置管理流程上做的更好，
其成熟度和企业级特性要强于Spring Cloud Config。Apollo相对于Nacos在配置管理做的更加全面，
Nacos则使用起来相对比较简洁，在对性能要求比较高的大规模场景更适合。但对于一个开源项目的选
型，项目上的人力投入（迭代进度、文档的完整性）、社区的活跃度（issue的数量和解决速度、
Contributor数量、社群的交流频次等），这些因素也比较关键。Apollo目前在国内开发者社区比较
热，在Github上有超过1w5颗星，在国内众多互联网公司有落地案例，可以说Apollo是目前配置中心产
品领域Number1的产品，所以从目前来看Apollo是最合适的配置中心选型。



