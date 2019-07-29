<template>
  <div class="conriner">
    <span class="iconfont" @click="change">{{icon}}</span>
    <span class="text">{{num}}</span>
    <span class="iconfont">&#xe654;</span>
    <span class="text">评论</span>
    <p class="time">13小时前</p>
    <template v-for="item in listData">
      <div class="list" :key="item.id">
        <span class="name">{{item.name}}</span>
        <span class="content">:  {{item.content}}</span>
      </div>
    </template>
    <div class="footer" @click="pullChange">
      <span class="pull">{{pull}}</span>
      <span class="iconfont pull-icon">{{icon2}}</span>
    </div>    
  </div>  
</template>
<script>
// 模拟数据
let commentDatas=[
  {id:1,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:2,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:3,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:4,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:5,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:6,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:7,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:8,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:9,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'},
  {id:10,name:'星星点灯',content:'每天上下班顺两颗，一周下来相当于节约了两棵树。'}
]
export default {
  data(){
    return {
      num:10,
      icon:'\ue605',
      flag:true,
      listData:[],
      pull:'查看全部评论',
      icon2:'\ue600',
      pullFlag:true
    }
  },
  created(){
    this.listData=commentDatas.slice(0,3)
  },
  methods:{
    change(){
      if(this.flag){
        this.icon='\ue62e'
        this.num++
        this.flag=false
      }else{
        this.icon='\ue605'
        this.num--
        this.flag=true
      }      
    },
    pullChange(){
      if(this.pullFlag){
        this.listData=commentDatas
        this.pull='收起'
        this.icon2='\ue621'
        this.pullFlag=false
      }else{
        this.listData=commentDatas.slice(0,3)
        this.pull='查看全部评论'
        this.icon2='\ue600'
        this.pullFlag=true
      }
    }
  }  
}
</script>
<style scoped>
.container .iconfont{
  display: inline-block;
  width: 17px;
  height: 17px;
  background-color: #fff0f0;
  padding: 2px;
}
.text{
  display: inline-block;
  width: 54px;
  margin:0 4px;
  font-size: 12px;
  color: #80858c;
  line-height: 17px;
  height: 17px;
  background-color: #fff0f0;
  padding: 2px;
}
.time{
  font-size: 12px;
  color: #ABC1B7;
  line-height: 17px;
  margin: 12px 0 8px 0;
  background-color: #fff0f0;
  width: 70px;
  padding: 2px;
}
.list{
  background-color: #fff0f0;
  margin-bottom: 4px;
  padding: 2px;
}
.name{
  font-size:14px;
  color: #5bafff;
}
.content{
  font-size: 14px;
  color: #41454d;
}
.pull{
  font-size: 12px;
  color: #acb1b7;
  background-color: #fff0f0;
  padding: 2px;
}
.pull-icon{
  font-size: 12px !important;
  line-height: 12px;
  height: 12px !important;
}
</style>
