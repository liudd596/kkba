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
        </tr>
        <tr v-for="(item,index) in courseList" :key='item.id'>
          <td>{{item.name}}</td>
          <td>{{item.price}}</td>
        </tr>
      </table>
      <h2>购物车</h2>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title1: '购物车',
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
    }
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
