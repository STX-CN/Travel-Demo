<template>
<div>
  <home-header :city="city"></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :list="iconList"></home-icons>
  <home-recommend :list="recommendList"></home-recommend>
  <home-weekend :list="weekendList"></home-weekend>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data: function () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted: function () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo: function () {
      axios.get('api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc: function (res) {
      res = res.data
      if (res.ret && res.data) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  }

}
</script>
<style>
</style>
