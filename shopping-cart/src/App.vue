<template>
  <div id="app">
    <h1>{{title1}}</h1>
    <div>
      <div><span>课程名称</span><input type="text" v-model="courseInfo.name"></div>
      <div><span>课程价格</span><input type="text" v-model="courseInfo.price"></div>
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
      <cart></cart>
      <hr>
      <div>{{ msg.split('').reverse().join('') }}</div>
      <div v-html="hello"></div>
      <a :href="url">{{url_name}}</a>
      <div :class="cla">sds </div>
      <div v-if="flag">孙悟空</div>
      <div v-else>tongbu</div>
      <div v-show="Apple">{{msg}}</div>
      <div v-for="(list,index) in courseList" :key="index">

        <div>{{list.name}}&nbsp;&nbsp;&nbsp;{{list.price}}&nbsp;&nbsp;&nbsp;{{list.id}}</div>
       
      </div>
      <button @click="liuddss">liudd</button>
      <br>
      {{msg}}
    </div>
  </div>
</template>

<script>
import cart from './components/cart';
export default {
  name: 'app',
  data () {
    return {
      title1: '购物车',
      msg: '香蕉banner',
      url_name: '百度',
      url: "http://www.baidu.com",
      cla: "sss",
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
      ]
    }
  },
  methods:{
    addcourseTolist () {
       this.courseList.push(this.courseInfo)
    },
    addCourseToCare () {

    },
    liuddss () {
     // this.courseList.push({ message: 'Baz' })
    }
  },
  components: {
    cart
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
