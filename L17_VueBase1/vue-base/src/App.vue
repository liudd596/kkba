<template>
  <div id="app">
    <h5 class="content">
      <p>5.v-if VS v-show
  v-if 是“真正”的条件渲染，因为它会确保在切换过程中条件块内的事件监听器和子组件适当的被销毁和重建。
  v-if 也是“惰性”的：如果在初始条件渲染为假，则什么也不做一直到条件变为真，才渲染。
  相比之下，v-show 就简单的多--不管初始条件是什么，元素总会被渲染，并且只是基于css进行切换。
  一版来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。
  因此，如果要频繁的切换，则使用v-show较好；如果在运行时条件很少改变，则使用 v-if 较好。</p>
<p>6.列表循环
  v-for </p>
<p>7.事件处理
  1.事件改变data数据，data数据改变会引起视图的变化
  2.事件传递参数
    $event
  3.数组更新检测
    看是返回原数组还是一个新数组
    变异方法：
        改变原数组，则引起视图更新 push()，pop()，unshift(),shift(),splice(),sort(),reverse()
    非变异方法：
        不改变原数组，创建新数组，则无法引起视图更新 filter() concat() slice()</p>
<p>
  8.计算属性
  computed 与 methods 的区别
</p>
<p>
  9.class 与 style 绑定
</p>
<p>
  10.表单 与 侦听器
  修饰符：
  .lazy
  .number
  .trim
  watch:监听事件
</p>
<p>
  11.子组件 Prop
  camelCase (驼峰命名法) 的 prop 名需要使用其等价的 kebab-case (短横线分隔命名) 命名
  
</p>
<p>
12.组件传递数据，只是单纯的传递数据
</p>
<p>
13.插槽slot,传递的是视图层
</p>
</h5>
    <v-header></v-header>
    <blogPost :titleProps='titleProps'></blogPost>
    <slotDemo>
       <template>
         <div>
           我是slot插槽哦！！我可以把视图传给子组件
         </div>
       </template>
       <template v-slot:button>
         <div>
           按钮
         </div>
       </template>
       <template v-slot:liudd>
         <div>
             我是slot<span :class="{red}">具名</span>插槽哦
         </div>
       </template>
    </slotDemo>
    <br>
    <!-- <button type="submit">
      <slot name="button">Submit</slot>
    </button> -->
    <!-- <BaseIcon></BaseIcon>
    <BaseButton></BaseButton> -->
    <!-- <base-icon></base-icon> -->
  </div>
</template>

<script>
import slotDemo from './components/soltDemo'
import header from './components/header'
import blogPost from './components/blogPost'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      titleProps: '我要传递数据给子组件(需重新运行项目哦)',
      red:true
    }
  },
  components:{
    blogPost,
    'v-header':header,
    slotDemo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.content{
  text-align: left;
  font-size: 15px
}
.red{color: red}
</style>
