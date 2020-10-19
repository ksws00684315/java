# Spring Cloud GateWay

### 三大核心

#### Route(路由)

路由是构建网关的基本模块，它由ID，目标URI，一系列的断言和过滤器组成，如果断言为true，则匹配该路由

### Predicate(断言)

参考的是Java8的java.util.function.Predicate

开发人员可以匹配HTTP请求中的所有内容（例如请求头或请求参数），如果请求与断言相匹配则进行路由

### Filter(过滤)

指的是Spring框架中GatewayFilter的实例，使用过滤器，可以在请求被路由前或者之后对请求进行修改。 

## 核心逻辑

路由转发+执行过滤器链

客户端向Sring Cloud Gateway发出请求。然后在Gateway Handler Mapping中找到与请求相匹配的路由，将其发送到Gateway Web Handler。

Handler 再通过制定的过滤器链来将请求发送到我们实际的服务执行业务逻辑，然后返回。