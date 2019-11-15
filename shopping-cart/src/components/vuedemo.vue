<template>
  <div>
    <h2>vuedemo组件</h2>
    <div>
        <!-- 计算属性 computed -->
        {{getMsg}}
        <!-- 方法 methods -->
        {{mMsg()}} 
        <p>{{fullName}}</p>
    </div>
    <h3>{{titleprops}}</h3>
  </div>
</template>

<script>

  export default {
    name:'vuedemo',
    props:['titleprops'],
    data () {
      return {
         msg: "helloliudd",
         firstName: 'Foo',
         lastName: 'Bar'
      };
    },

    components: {},
    // 计算属性 基于它们的响应式依赖进行缓存的,数据改变时才会更新。例如：遍历一个巨大的数组并做大量的计算
    computed: {
        // 如果数据没有被改变，则不会重新计算
        getMsg(){
            return this.msg.split('').reverse().join('')
        },
        fullName(){
            return this.firstName + " " + this.lastName; 
        }
    },

    beforeMount() {},

    mounted() {},
    // 方法 每当触发重新渲染时，调用方法将总会再次执行函数，没有缓存
    methods: {
        mMsg(){
            return this.msg.split('').reverse().join('')
        }
    },

    watch: {}

  }

</script>
<style lang='' scoped>

</style>