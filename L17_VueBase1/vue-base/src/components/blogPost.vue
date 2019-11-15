<template>
  <div :class="{blogclass:blogclass}">
    <p :style="{fontSize:num+'px'}">我是blogPost<span :style="{color:colorRed}">插槽</span>子组件哦！</p>
    {{titleProps}}
  </div>
</template>

<script>
  export default {
    name:'',
    props:['titleProps'],
    data () {
      return {
        colorRed: "red",
        num: 15,
        blogclass: true
      };
    },

    components: {},

    computed: {},

    beforeMount() {},

    mounted() {},

    methods: {},

    watch: {}

  }

</script>
<style lang='' scoped>
.blogclass{font-weight:600}
</style>