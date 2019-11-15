<template>
  <div>
    <p>我是helloword子组件</p>
    <p>
        axios获取数据
    </p>
  </div>
</template>

<script>
  export default {
    name:'helloworld',
    props:[''],
    data () {
      return {
         msg:'hahahha'
      };
    },
    mounted() {
        // this.$axios.get("http://www.phonegap100.com/appapi.php",{
        //     params:{
        //         a:"getPortalList",
        //         catid: 20,
        //         page: 1
        //     }
        // })
        // .then(res => {
        //     console.log(res);
        // })
        // .catch(error => {
        //     console.log(error)
        // })
        this.$axios({
            method: 'get',
            url: 'http://apicloud.mob.com/v1/mobile/address/query?key=2799678a59dbc&phone=1814192'
        })
        .then(res => {
            console.log(res.data)
        })
        .catch(error => {
            console.log(error)
        })
    },
    methods: {},
    components: {}
  }

</script>
<style lang='' scoped>

</style>