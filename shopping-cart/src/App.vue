<template>
  <div id="app">
    <h1>{{title1}}</h1>
    <hr>
    <div>
      <h2>{{title2}}</h2>
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
      <h2>{{title5}}</h2>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      title1: '购物车',
      title2: '添加课程',
      title5: '购物车',
      courseList: [
        {
          id: 0,
          courseName: 'web全栈开发架构师',
          coursePrice: 888
        },
        {
          id: 1,
          courseName: 'Python人工智能',
          coursePrice: 999
        }
      ]
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
