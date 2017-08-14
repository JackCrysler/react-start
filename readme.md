react  

1.  jsx 语法 类似于html  实质是：React.createElement(type,attr,children)的语法糖

2.  创建react component的方式：function 或者 class(面向对象)；推荐使用class方式。  
    //如果不用es6的class可以使用:    

        React.createClass({
            render(){

            }
        })

    来创建class模块

    //this问题
    使用ES6的class去创建模块，需要把定义好的jsx函数通过bind绑定this指针，或者直接使用箭头函数，推荐使用箭头函数

3.  属性props值可以是字符串、变量、表达式，变量和表达式用{}括起来

4.  props由组件外界传到组件内部的属性或者方法，在组建内部不建议修改props的值;

    state是组件本身所具有的属性或者方法, 改变state使用setState(),继承自React.component;

    * *已经有props为何还要state？ react理念，保持数据流的单一性，为将来构建大型项目做良好的准备* 
    
    纯函数和非纯函数：

        function test(a,b){//纯
            return a+b
        }

        function test(a,b){//非纯
            a = 1;
            return a+b
        }

5. 事件绑定要用驼峰写法 onClick  onInput 

6. 样式设置

7. 生命周期

        创建期

            componentWillMount
            componentDidMount

        存在期

            shouldComponentUpdate(必须返回值),   
            componentWillUpdate,    
            dom rerender,
            componentDidUpdate
        

8. 列表循环 数据请求

9. 父=>子 子=>子

10. ref获取实际dom，在mount时执行



