<template>
  <div id="app">
    <h1>{{title1}}</h1>
    <div>
      <div><span>课程名称</span> <input type="text" v-model="courseInfo.name"></div>
      <div><span>课程价格</span> <input type="text" v-model="courseInfo.price"></div>
      <div><input type="button" value="添加课程到列表" v-on:click="addcourseTolist"></div>
    </div>
    <hr>
    <div>
      <h2>添加课程</h2>
      <table>
        <tr>
          <th>课程名称</th>
          <th>课程价格</th>
          <th>操    作</th>
        </tr>
        <tr v-for="(item,index) in courseList" :key='item.id'>
          <td>{{item.name}}</td>
          <td>{{item.price}}</td>
          <th><button @click="addCourseToCare(index)">添加到购物车</button></th>
        </tr>
      </table>
      <!-- 新组件 -->
      <cart :title="title"></cart>
      <hr>
      <div>{{ msg.split('').reverse().join('') }}</div>
      <div v-html="hello"></div>
      <a :href="url">{{url_name}}</a>
      <div :class="cla">添加一个class类名 </div>
      <div v-if="flag">孙悟空</div>
      <div v-else>通臂猿猴</div>
      <div v-show="Apple">{{msg}}</div>
      <div v-for="(list,index) in courseList" :key="index">

        <span>{{list.name}}&nbsp;&nbsp;&nbsp;{{list.price}}&nbsp;&nbsp;&nbsp;{{list.id}}</span>
       
      </div>

      <ul v-for="(name,index) in names" :key="name.id">
        <li>{{index}}</li>
        <li>{{name.name}}</li>
        <li>{{name.age}}</li>
      </ul>
      <button @click="liuddss('哈哈哈哈哈哈',$event)">liudd</button>
      <ul>
        <li v-for="(hello,index) in hellos" :key="index">{{hello}}</li>
      </ul>
      <button @click="addhandler()">按钮</button>
    </div>
    <hr>
    <vuedemo :titleprops="titleprops"></vuedemo>
  </div>
</template>

<script>
import cart from './components/cart';
import vuedemo from './components/vuedemo'
export default {
  name: 'app',
  data () {
    return {
      titleprops: 'my name liudd 子组件传递数据',
      title:{
        name:"小李2"
      },
      title1: '购物车',
      msg: '香蕉banner',
      url_name: '百度',
      url: "http://www.baidu.com",
      cla: "class2",
      flag: false,
      Apple: true,
      // 解析HTML结构
      hello: '<h3>liudd</h3>',
      courseInfo: {
        name : '',
        price : ''
      },
      courseList: [
        {
          id: 0,
          name: 'web全栈开发架构师',
          price: 888
        },
        {
          id: 1,
          name: 'Python人工智能',
          price: 999
        }
      ],
      names: [
        {
          name: "小李",
          age: 22
        },
        {
          name: "小王",
          age: 23
        },
        {
          name: "小天",
          age: 20
        }
      ],
      hellos: ['hello1','hello2','hello3','hello4','hello5']
    }
  },
  methods:{
    addcourseTolist () {
       this.courseList.push(this.courseInfo)
    },
    addCourseToCare () {

    },
    liuddss (data,$event) {
      this.names.push({ name: 'Baz', age: 18 });
      this.flag = true;
      console.log(this);
      console.log(data);
      console.log($event);
    },
    addhandler() {
      this.hellos.push("helloliudd")
    }
  },
  components: {
    cart,
    vuedemo
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
</style>

<!--

5.v-if VS v-show
  v-if 是“真正”的条件渲染，因为它会确保在切换过程中条件块内的事件监听器和子组件适当的被销毁和重建。
  v-if 也是“惰性”的：如果在初始条件渲染为假，则什么也不做一直到条件变为真，才渲染。
  相比之下，v-show 就简单的多--不管初始条件是什么，元素总会被渲染，并且只是基于css进行切换。
  一版来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。
  因此，如果要频繁的切换，则使用v-show较好；如果在运行时条件很少改变，则使用 v-if 较好。
6.列表循环
  v-for 
7.事件处理
  1.事件改变data数据，data数据改变会引起视图的变化
  2.事件传递参数
    $event
  3.数组更新检测
    看是返回原数组还是一个新数组
    变异方法：
        改变原数组，则引起视图更新 push()，pop()，unshift(),shift(),splice(),sort(),reverse()
    非变异方法：
        不改变原数组，创建新数组，则无法引起视图更新 filter() concat() slice()
8.计算属性
  computed 与 methods 的区别
9.class 与 style 绑定
10.表单 与 侦听器
  修饰符：
  .lazy
  .number
  .trim
  watch:监听事件
11.子组件 Prop
  camelCase (驼峰命名法) 的 prop 名需要使用其等价的 kebab-case (短横线分隔命名) 命名
  
12.组件<v-header></v-header>传递数据，只是单纯的传递数据
13.插槽slot,传递的是视图层
  
  
   
  
  
  
  -->