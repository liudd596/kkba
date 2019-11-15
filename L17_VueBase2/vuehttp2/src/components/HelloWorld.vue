<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  // mounted(){
    // 不需要跨域处理的接口
  //   this.$axios.get('http://www.phonegap100.com/appapi.php?a=getPortalList&catid=20&page=1')
  //   .then(res => {
  //     console.log(res.data)
  //   })
  //   .catch(error => {
  //     console.log(error)
  //   })
  // }
  mounted(){
    // 跨域处理
    var url = this.HOST + 'v1/mobile/address/query?key=2799678a59dbc&phone=1814192'
    this.$axios({
      method: 'get',
      url: url
    })
    .then(res => {
      console.log(res.data)
    })
    .catch(error => {
      console.log(error)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
