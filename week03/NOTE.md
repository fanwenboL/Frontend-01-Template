# 每周总结可以写在这里
Javascript
语句
completion Record 
[[type]]  语句完成的类型：normal break continue return throw
[[value]] 七种语言类型：Types(有可能为空) return throw用
[[target]] lable 循环break和continue用

简单语句
表达式语句：ExpressionStatement 计算
    a = 1 + 2;
空语句：EmptyStatement
    ;
断点：DebuggerStatement
    debugger
ThrowStatement  可以跟一个表达式
    throw a;
ContinueStatement
    continue lable1(标签名，必须是合法的标识符，和变量一样)
BreakStatement
    break  lable1(标签名，必须是合法的标识符，和变量一样)
ReturnStatement
    return 1+2

复合语句
BlockStatement  块级作用域
    <script>
        {
            a: 1
        }
        不会被理解为一个对象 
    </script>
    会把多条语句从语法中扩起来，变成一条语句。为 let const提供作用域
Iteration 循环语句
    会独立产生作用域   
    eg for(let i = 0;i<10;i++) {
        let 定义的每次都会产生新的i
    }
    while(){如果有return throw，会变成return throw，如果是有break continue会消费掉，会做处理}
    do()while() 至少会执行一次
    for(){}
    for ( in ) {} 遍历对象
    for ( of ) {} 遍历任何有迭代对象的东西 配合
        for of =》Iterator=》Generator/Array
            var不受块级作用域影响，写在函数作用域任何地方
    for await( of ) {
        // 
    }

try
try{

} catch(){

} finally {

}

声明
function foo() {}
function* foo() {} 可返回多个值的函数  与async无关
async function
async function*




js对象机制
    唯一标示性 identifier   
    动态的状态可以改变  state
    拥有行为 behavior
        [封装（不容易修改细节），复用（可以重复使用），解偶（不同模块关联性），内聚。
        继承
        多态（动态性程度）]
Object-Class(oc-c++-java)
归类（产生多重继承），分类（产生基类）
interface 接口
mixins 多重继承

javascript-prototype

objectAPI
{}.[] Object.defineProperty  最原始的对象
Object.creat/Object/setPrototypeOf/Object.getPrototypeOf es5 
new/class/extends es6
new/function/prototype 
