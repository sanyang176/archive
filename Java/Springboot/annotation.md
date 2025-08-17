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
aspect 一般跟component混用<br />
before 在切面方法之前执行<br />
after 在切面方法之后执行<br />
afterreturning 在切面方法返回之后执行<br />
afterthrowing 在切面方法抛出异常之后执行<br />
around 在切面方法执行时添加前后逻辑<br />
pointcut用来修饰方法，格式为"execution(* com.java.110.Test1.*(...))"<br />
order，使用时@Order(1)，数字越小越优先执行<br />
aop注解里面的参数：
execution(* com.java.110.Test1.*(...))，第一个*表示方法返回值为任意类型，第二个*表示Test类中的任意方法，(...)表示方法参数为任意。对于方法名，也可以使用*匹配，如*To表示所有以To结尾的方法
execution表示满足匹配的所有目标类方法
@annotation表示标注了特定注解的目标方法的连接点
args：按照方法参数类型匹配
@args：表示具有特定注解的参数
# 单元测试相关注解:
springboottest 单元测试启动完整的springboot<br />
test 标注方法为测试方法<br />
before/after 在测试方法之前/之后执行<br />
beforeclass/afterclass 再所有测试方法之前/之后执行<br />
多个参数的测试方法，类似C#xunit中的theory<br />
```
@ParameterizedTest
@ValueSource(ints = {1, 2, 3})
void testWithValueSource(int argument) {
    assertTrue(argument > 0 && argument < 4);
}
```
@Ignore：所修饰的测试方法会被测试运行器忽略。<br />
@RunWith：可以更改测试执行器使用junit测试执行器。<br />
# Mockito相关：
mock(Class<T> classToMock)：创建一个类的模拟对象。这是创建模拟对象的基础。<br />
when(T methodCall)：当你想模拟一个方法调用的返回值时使用。与thenReturn一起使用，可以指定一个方法调用应该返回什么值。<br />
thenReturn(T value)：与when方法一起使用，用于指定方法调用的返回值。<br />
doReturn(Object toBeReturned)：一个替代thenReturn的方法，用在当你需要模拟void方法或在spy对象上进行模拟时。<br />
verify(T mock)：用于验证某个模拟对象的某个方法是否被调用，以及调用的次数。<br />
any()：在设定模拟行为（如when）或验证（如verify）时，用于表示任何类型和值的参数。<br />
eq(T value)：用于指定方法调用时期望的具体参数值。<br />
doNothing()：用于模拟void方法时，指定该方法不执行任何操作。<br />
doThrow(Throwable... toBeThrown)：用于模拟方法调用时抛出异常。<br />
spy(T object)：创建一个真实对象的“间谍”或“spy”。这允许你在真实对象上“监视”方法调用，同时还能够覆盖某些方法的行为。<br />
ArgumentCaptor<T>：用于捕获方法调用时传递的参数，以便后续进行断言。<br />
times(int wantedNumberOfInvocations)：与verify方法一起使用，用于指定某个方法被调用的具体次数。<br />
never()：与verify一起使用，用于验证某个方法从未被调用过。<br />
举例：
```
@ExtendWith(MockitoExtension.class)
public class PaymentServiceTest {

@mock
private ProcessorService processorService;
@InjectMocks
private PaymentService paymentService;
@Test
public void ShouldGetPaymentProsessor(){
    when(processorService.GetProcessor()).thenReturn(1);
    var result = paymentService.GetPayment();
    assertEquals(result,2);
    }
}
```
