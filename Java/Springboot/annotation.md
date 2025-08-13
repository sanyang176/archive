## 普通注解
repository<br />
component<br />
resource<br />
primary<br />
postconstruct<br />
postdestory<br />
requsetmapping/requestbody/responcebidy/requestparam<br />
pathvariable<br />
requestpart<br />
requestcontroller/getmapping/postmapping<br />
configuration标注某个类为配置类<br />
conponentscan<br />
enablecaching<br />
value对数值进行依赖注入<br />
configurationproperties<br />
conditional<br />
enabletransactionmanagerment<br />
transactional<br />
enablewebsecurity<br />
enableglobalmethodsecurity<br />
controlleradvice<br />
SpringBootApplication 启动类<br />
EnableAutoConfiguration在启动类中隐式包含，读取META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports路径下的类名，在springapplication.run时，内部调用loadfactories加载所有autoconfiguration类<br />
contorller控制器，<br />
requestmapping 管理请求的，可以定义请求类型等<br />
service服务 <br />
mapping dao层<br />
configuration 代码形式的配置文件<br />
bean标注一个属性/方法，可以给spring管理<br />
autowired 依赖注入其他service，按照type查找<br />
resource 可以按照name查找，也可以按照type查找<br />
Qualifier 可以获取指定的接口实现<br />
scope定义Bean的生命周期，单例，原型类型<br />
lazy懒加载<br />
transaction启动事务管理<br />
value 注入常量<br />
component 泛指，controller，service，configuration这些都属于componrnt<br />
pathvariable url路径变量<br />
entity 标注的实体类<br />
table 数据库表名<br />
repository 具有更高抽象的方法，一般mapping里面是简单的增删改查<br />
exceptionhandler 方法注解，遇到异常<br />
## AOP 相关注解:
aspect<br />
before 在切面方法之前执行<br />
after 在切面方法之后执行<br />
afterreturning<br />
afterthrowing<br />
around 在切面方法执行时添加前后逻辑<br />
pointcut<br />
order<br />
## 单元测试相关注解:
springboottest 单元测试启动完整的springboot<br />
test 标注方法为测试方法<br />
