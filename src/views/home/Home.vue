<template>
  <div id="home">
    <nav-bar><div slot="center">购物街</div></nav-bar>
    <HomeSwiper :banners="banners"></HomeSwiper>
    <Recommends :recommends="recommends"></Recommends>
  </div>
</template>

<script>
  import NavBar from "../../components/common/navbar/NavBar";
  import HomeSwiper from "./childComps/HomeSwiper";
  import {getHomeMultidata} from "../../network/home";
  import Recommends from "./childComps/Recommends";

  export default {
    name: "Home",
    components: {
      Recommends,
      HomeSwiper,
      NavBar,
    },
    data() {
      return {
        banners: [],
        recommends: []
      }
    },
    created() {
      this.getHomeMultidata()
    },
    methods: {
      getHomeMultidata() {
        getHomeMultidata().then(res => {
          // this.result = res;
          this.banners = res.data.banner.list;
          this.recommends = res.data.recommend.list;
        })
      },
    }

  }
</script>

<style scoped>

</style>
