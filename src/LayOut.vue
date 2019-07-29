<template>
  <!-- 头部 -->
  <div>
    <mt-header title="车友圈">
      <router-link to="/" slot="left">
        <mt-button icon="back">发现</mt-button>
      </router-link>
      <mt-button icon="more" slot="right"></mt-button>
    </mt-header>
    <!-- 背景图片 -->
    <div class="banner">
      <img :src="require('@/assets/friendcircle-banner.png')" alt="">
      <div class="badge">
        <span>张小六</span>
        <img :src="require('@/assets/friendcircle-banner.png')" alt="">
        <mt-badge type="error" size="small" class="num">10</mt-badge>
      </div>
    </div>
    <!-- 评论 -->
    <Comments :keys="1"/>
    <Comments :keys="4"/>
    <Comments :keys="7"/>
  </div>
</template>
<script>
import Comments from './components/Comments'
export default {
  name: "LayOut",
  components:{
    Comments
  }
};
</script>
<style scoped>
  .mint-header{
    background-color: #3a3c3f;
  }
  .banner{
    width: 100%;
    height: 210px;    
    position: relative;
  }
  .banner img{
    height: 210px;
  }
  .badge{
    position: absolute;
    right: 16px;
    bottom: 16px;
    display: flex;
  }
  .badge span{
    display: block;
    line-height: 48px;
    font-size: 16px;
    color:#fff;
    text-shadow: 1px 1px 5px rgba(0, 0, 0, 70%);
    margin-right: 12px;
  }
  .badge img{
    display: block;
    width: 48px;
    height: 48px;
    border-radius: 4px;
  }
  .num{
    display: block;
    line-height: 15px!important;
    height: 15px;
    margin-left: -20px;
  }
</style>
