---
layout: post
title: 经典架构S（Struts）S（Spring）H（Hibernate）的优缺点
description:
- 经典架构S（Struts）S（Spring）H（Hibernate）的优缺点
categories:
- 无
---
###Spring
Spring为解决企业应用开发复杂性而创建
####主要优势之 分层架构
   使层与层之间和类与类之间的关系，由原来的强绑定与强耦合转变为不绑定和松耦合，直接面向接口编程，把设计与实现相分离的原则发挥到极致
   使得J2EE每个层之间的模块职能更加清，对于单元测试也产生了很深远的影响
   Spring出现前，如果某个模块没有完成，做单独模块的单元测试还是很困难的

####缺点
   大型项目的开发，Spring使原来难以维护的类与类之间的强耦合关系，转变为更加难以维护的XML文件配置，工作量巨大且容易出错
   随着每个应用模块的升级，这些模块之间的版本，可能没有正确同步更新，对于同一个公共组件，有的模块用的可能是1.0版本，而另外一个功能模块用的可能是2.0版本，可怕的是1.0版本和2.0版本之间，可能还不兼容，Spring对于这些需求，就无能为力了

   Spring加入了OSGI标准的实现，也是为了解决不同版本之间同时存在的这些问题
   随着Spring加入的功能越来越多，Spring也就失去了轻量开源框架的特点，变得越来越笨重

   虽然Spring也支持了所谓的免配置，可以通过@Autowired标签自行绑定
   还可以通过<property name="packagesToScan" value="com.demo.entity" /> 
   设置自动绑定加载所有的Hibernate对象，但是如果这些上百个或者数十个中的任何一个Entity对象加载失败，则整个Spring服务就启动不起来了，这与难于部署的EJB有啥区别呢？
   
   令人可笑的是，由于使用了@Autowired标签，相当一部分开发人员不再面向接口编程了，对于 Class A的实例，美其名曰由Spring自行绑定，接口也好，实际实现类也好，就在Spring配置一下就可以了
   而Spring最核心的就是面向接口编程和 IOC，没有了面向接口编程，用一个A a=new A() 来实例化一个Class，有什么不可以呢？少写了一行代码，引入了一个重量级的Spring，究竟为啥使用Spring呢？

###Hibernate
   Hibernate的流行，则是由于开发人员和客户，对于Entity EJB（实体EJB）臃肿的身材及部署的困难，是在极度失望情绪下造成的
   既然是轻量级解决方案，那么分布式就不是可选项，没有分布式，那么EJB就无用武之地了
   Rod Johnson就因为强调绝大部分企业应用是不需要分布式的，从而推出了自己轻量级的Spring解决方案
   最近随着云计算架构的兴起， 架构是否支持分布式，又是必选项了
   
   技术架构的选型，就跟法国巴黎流行时装一样，真是典型的十年河东，十年河西
   所以，像 SOA、云计算、SaaS、物联网这些大名词，不仅会给客户带来很大的困惑，同样也会给程序员、系统分析师、系统架构师、技术总监带来困惑。从肯定到否 定，再到自我否定，真是符合大自然螺旋式上升的发展规律

###Struts
   Struts一经推出，几乎打败了当时的所有竞争对手
   其伟大之处，在于它对网页数据的动态绑定
   虽然数据绑定不是一个新名词，微软在1991年推出Visual Basic1.0的时候，就创造性地发明了让VB程序员又爱又恨的数据绑定，但是对于Web 编程，Struts也还是把数据绑定首次应用到了Web编程上
   它能够让人们用Set和Get的形式取得网页数据，而不是单一的黑盒式的 request.getParameter()，从而使得网页数据取值进入面向对象（OO）化时代


