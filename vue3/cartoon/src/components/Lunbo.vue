<template>
    <div class="swipe-container">
      <van-swipe :autoplay="3000" lazy-render>
      <van-swipe-item v-for="(comic, index) in comics" :key="index">
        <img 
          :src="comic.image" 
          class="swipe-image" 
          @click="goToRead(comic.id)"
        />
      </van-swipe-item>
    </van-swipe>
  </div>
</template>

<script>
import lunbo1 from "../assets/lunbo/lubo1.jpg"
import lunbo2 from "../assets/lunbo/lubo2.jpg"
import lunbo3 from "../assets/lunbo/lubo3.jpg"
export default{
  data() {
    return {
      comics:[
        { id:1 , image:lunbo1 },
        { id:2 , image:lunbo2 },
        { id:3 , image:lunbo3 },
      ]
    }
  },
  methods:{
    //跳转
    goToRead(comicId){
      this.$router.push({ name: 'read', params: { id: comicId , chapterId: 1 } });
    },
  },
}

</script>

<style scoped>
.swipe-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.van-swipe-item {
  display: flex; /* 或 display: grid; */
  justify-content: center; /* 如果使用 Flexbox */
  align-items: center;     /* 如果使用 Flexbox */
}

.swipe-image {     
  height: 400px;       /* 设定统一高度 */
  object-fit: cover;
}
</style>
