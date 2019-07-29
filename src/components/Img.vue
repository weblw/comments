<template>
  <div class="container">
    <template v-for="item in imgData">
      <img :key="item.id" :src="item.src" alt :style="'width:'+width+';'+'height:'+height" />
    </template>
  </div>
</template>

<script>
export default {
  props:['imgData'],
  data() {
    return {      
      width: "172px",
      height: "172px"
    };
  },
  created() {
    if (Array.isArray(this.imgData)) {
      if (this.imgData.length == 1) {
        this.width = "172px";
        this.height = "172px";
      } else if (this.imgData.length == 2 || this.imgData.length == 4) {
        this.width = "134px";
        this.height = "134px";
      } else if (this.imgData.length == 3 || this.imgData.length >= 5) {
        this.width = "88px";
        this.height = "88px";
      }
    }
  }
};
</script>
<style scoped>
.container {
  margin: 8px 39px 12px 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  width: 100%;
}
.container img{
  margin: 0 4px 4px 0;
}
</style>
