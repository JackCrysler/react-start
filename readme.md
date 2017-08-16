react  

1.  jsx语法，类似于html。它的实质是：React.createElement(type,attr,children)的语法糖

2.  创建react component的方式：function 或者 ES6-class（推荐使用class方式）。  
    
    * 如果不用es6的class可以使用：  

            React.createClass({  
                    
                render(){
                        
                }  

            }) 

    * this问题  

        使用ES6的class去创建组件，需要把定义在jsx上的函数bind(this)，或者直接使用箭头函数。

3.  ReactDOM.render()用于把react创建的虚拟dom渲染到浏览器中。

4.  props是由组件外界传到组件内部的属性或者方法，在组建内部不建议修改props的值。属性props值可以是字符串、变量、表达式、函数，变量和表达式用{}括起来;

    state是组件本身所具有的属性或者方法, 改变state使用setState(),继承自React.component;

    * *已经有props为何还要state？ react理念，保持数据流的单一性，在组件内部不能直接修改传入的props，为构建大型项目做基础* 
    
    纯函数和非纯函数：

        function test(a,b){//纯：入参是只读的
            return a+b 
        }

        function test(a,b){//非纯：函数内部修改了入参
            a = 1;
            return a+b
        }

    * *当你想要实现继承时，不妨试试组件拼装。props.children类似于vue的slot插槽*

5. 事件绑定要用驼峰写法 onClick  onInput 

6. 样式设置，在react中以对象的形式设置样式，驼峰命名法，赋值给组件元素的style属性即可

7. 生命周期

        * ES6 Class创建的component

            创建期

                componentWillMount
                componentDidMount

            存在期

                componentWillRecevieProps
                shouldComponentUpdate(必须返回值),   
                componentWillUpdate,    
                dom rerender,
                componentDidUpdate
            
        * React.createClass({})创建的component

            创建期

                getDefaultProps
                getInitialState
                componentWillMount
                componentDidMount

            存在期

                componentWillRecevieProps
                shouldComponentUpdate
                componentWillUpdate
                componentDidUpdate

            销毁期

                componentWillUnmount

    * *注意：一定不要在componentWillUpdate或者componentDidUpdate这样的生命周期中去执行setState()操作，会导致闭环。*        

8. 
    列表循环：在插值表达式{}中放数组，数组中放子组件即可;

    数据请求：在componentDidMount生命周期钩子中进行ajax请求；也可以在外面完成数据请求之后调用ReactDOM.render()

9.      
    父=>子： props 单项数据流

    子=>子： 状态提升 子组件的状态提升到共有父state中

10. ref属性存放指定的实际dom元素，在componentDidMount时执行

11. react中将字符串作为innerHTML的值输出使用dangerouslySetInnerHTML属性，它的值是一个函数如：

        function info2(){
            return {
                __html:'<div>html字符串</div>'
            }
        }

    其中__html用来配置将要输出的具体内容





