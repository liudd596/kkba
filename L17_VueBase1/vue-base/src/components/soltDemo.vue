<template>
  <div>
    <slot></slot>
    <slot name="liudd">
        <div>我是具名插槽有name属性，我的父组件template需有v-slot:liudd</div>
    </slot>
    <br>
    <button type="submit">
      <slot name="button"></slot>
    </button>
    <hr>
    <slot :ct="ct"></slot>
    <br>
  </div>
</template>

<script>

  export default {
    name:'slotdemo',
    props:[''],
    data () {
      return {
       ct:'liudd'
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

</style>