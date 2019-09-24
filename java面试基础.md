# 简介

学习后将掌握：巩固Java开发相关知识，提高面试通过率。
参考：https://edu.aliyun.com/roadmap/java?spm=a2c6h.12873581.1367612.2.24e91feb02gYFS&accounttraceid=d6db902c-cda7-4442-a0fc-864ed354bc7a

# 串讲一

## 集合

HashSet:是基于HashMap实现的，初始的hashMap的大小为16,

+ 拦截器（Interceptor）和过滤器（Filter）的执行顺序和区别

过滤器(Filter)：它依赖于servlet容器。在实现上，基于函数回调，它可以对几乎所有请求进行过滤，但是缺点是一个过滤器实例只能在容器初始化时调用一次。使用过滤器的目的，是用来做一些过滤操作，获取我们想要获取的数据，比如：在Javaweb中，对传入的request、response提前过滤掉一些信息，或者提前设置一些参数，然后再传入servlet或者Controller进行业务逻辑操作。通常用的场景是：在过滤器中修改字符编码（CharacterEncodingFilter）、在过滤器中修改HttpServletRequest的一些参数（XSSFilter(自定义过滤器)），如：过滤低俗文字、危险字符等。

拦截器（Interceptor）：它依赖于web框架，在SpringMVC中就是依赖于SpringMVC框架。在实现上,基于Java的反射机制，属于面向切面编程（AOP）的一种运用，就是在service或者一个方法前，调用一个方法，或者在方法后，调用一个方法，比如动态代理就是拦截器的简单实现，在调用方法前打印出字符串（或者做其它业务逻辑的操作），也可以在调用方法后打印出字符串，甚至在抛出异常的时候做业务逻辑的操作。由于拦截器是基于web框架的调用，因此可以使用Spring的依赖注入（DI）进行一些业务操作，同时一个拦截器实例在一个controller生命周期之内可以多次调用。但是缺点是只能对controller请求进行拦截，对其他的一些比如直接访问静态资源的请求则没办法进行拦截处理。

+ 动态代理的实现

常用的动态代理实现方式有两种，一种是利用JDK反射机制生成代理（InvocationHandler），另外一种是使用CGLIB代理

+ 定时任务
Timer
SpringTask
Quartz框架

+ 购物车实现
> session，cookie，数据库

+ 统计重名用户

分组统计
数据量大考虑位图索引
