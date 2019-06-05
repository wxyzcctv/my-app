<template>
<div id="app">
    {{msg}}
    <div>
        <input type="text" v-model='info'>
        <button @click='handClick'>添加</button>
    </div>
    <ul>
        <g-item v-for='item in list' :key="item" :item='item'></g-item>
    </ul>
</div>
</template>

<script>
import GItem from './components/GItem.vue'
export default {
  name:'app',
  components:{
    GItem,
  },
  data() {
    return {
      msg: 'hello  geektime',
      info: '',
      list: []
    }
  },
  methods:{
    handClick(){
        this.list.push(this.info)
        this.info = ''
    }
  },
}
</script>

<style>

</style>
