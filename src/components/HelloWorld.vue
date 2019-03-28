<template>
  <div class="hello">

    <div class="tab" >
        <div v-for="(item,index) in tabs" :key="index" @click="tabList(item)" :class="{active:currentTab == item}">
          {{item}}
        </div>
    </div>


    <component class="box" :is="currentTab"></component>
  </div>
</template>

<script>

import svgDemo from './demo1'

export default {
  components:{
			svgDemo
  },
  data () {
    return {
      currentTab: 'svgDemo',
      tabs:["svgDemo","demo_2","demo_3","demo_4"]
    }
  },
  methods:{
    tabList(item){
      this.currentTab = item
    }
  },
  mounted(){

  }

}
</script>
<style scoped>
.hello{
  display: flex;
  flex-direction: row;
}
.tab>div{
  margin: 10px;
}
.active{
  font-weight: bold;
}
</style>
