<template>
  <div id="app">
      {{msg}}
      <div>
          <input type="text" v-model='infor'>
          <button @click="handClick">添加</button>
          <ul>
              <g-item v-for="item in list" :key="item">
                <template v-slot:item="itemProps">
                  <span :style="{fontSize: '20px', color: itemProps.checked ? 'red': 'blue'}">{{item}}</span>
                </template>
                <!-- 整个template包裹的内容就是slot的内容，也是GItem中定义的slot
                     这里绑定了名为item的slot，并定义其属性名为itemProps，通过属性名
                     绑定样式的变化方式，这里的变化方式就是判定slot中的checked是否被
                     点中，如果被点中，样式就变为红色，没有被点中，样式为蓝色，此处实现
                     了数据向父组件传输，checked在GItem.vue中通过checkbox进行改变状态的，
                     并在GItem.vue中将checked的变化值传输到了其中的slot上
                 -->
              </g-item>
          </ul>
      </div>
  </div> 
</template>

<script>
import GItem from './components/GItem'
export default {
  name: "app",
  components: {
    GItem,
  },
  data(){
      return{
          msg:'hello geektime',
          infor:'',
          list:[]
      }
  },
  methods:{
      handClick(){
          this.list.push(this.infor)
          this.infor = ''
      }
  }
};
</script>

<style>

</style>
