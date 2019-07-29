<template>
  <div class="container">
    <div class="photo">
      <img :src="require('@/assets/friendcircle-banner.png')" alt="">
    </div>
    <div class="right">
      <p class="name">凌度</p>
      <p class="say">2017年，心之向往，记住我的西藏行，历时16天，川进青出。</p>
      <!-- 图片 -->
      <Img :imgData='imgData'/>
      <List />
    </div>
  </div>
</template>
<script>
import Img from './Img'
import List from './List'
// 模拟假数据
let imgDatas=[
  {keys:1,imgData:[
    { id: 1, src: require("@/assets/friendcircle-banner.png") }
  ]},
  {keys:4,imgData:[
    { id: 1, src: require("@/assets/friendcircle-banner.png") },
    { id: 2, src: require("@/assets/friendcircle-banner.png") },
    { id: 3, src: require("@/assets/friendcircle-banner.png") },
    { id: 4, src: require("@/assets/friendcircle-banner.png") }
  ]},
  {keys:7,imgData:[
    { id: 1, src: require("@/assets/friendcircle-banner.png") },
    { id: 2, src: require("@/assets/friendcircle-banner.png") },
    { id: 3, src: require("@/assets/friendcircle-banner.png") },
    { id: 4, src: require("@/assets/friendcircle-banner.png") },
    { id: 5, src: require("@/assets/friendcircle-banner.png") },
    { id: 6, src: require("@/assets/friendcircle-banner.png") },
    { id: 7, src: require("@/assets/friendcircle-banner.png") }
  ]}
]
export default {
  props:['keys'],
  data(){
    return {
      imgData: []
    }
  },
  created(){
    imgDatas.forEach(item=>{
      if(item.keys==this.keys){
        this.imgData=item.imgData
      }
    })
  },
  components:{
    Img,
    List
  }
}
</script>
<style scoped>
.container{
  padding: 16px;
  display: flex;
}
.photo{
  margin-right: 8px;
}
.photo img{
  width: 40px;
  height: 40px;
}
.right .name{
  font-size: 15px;
  font-weight: bold;
  color: #41454d;
  background-color: #fff0f0;
  margin-bottom: 2px;
}
.right .say{
  font-size: 14px;
  color: #41454d;
  background-color: #fff0f0;
  margin-bottom: 8px;
}
</style>
