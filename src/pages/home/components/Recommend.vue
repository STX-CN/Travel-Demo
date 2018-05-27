<template>
<div>
  <div class="title">热销推荐</div>
  <ul>
    <li class="item boder-bottom" v-for="item of recommendList" :key="item.id">
      <img class="item-img" :src="item.imgUrl"/>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看详情</button>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default{
  name: 'HomeRecommend',
  data: function () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/cd/cd5907320e7a1a1a.img.jpg_200x200_6de235db.jpg',
          title: '中国福州云顶',
          desc: '福建省福州市永泰县'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/c0/c016dce7a3156fd1.water.jpg_200x200_9e096461.jpg',
          title: '福清后溪漂流',
          desc: '福建省福州市福清市'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/76/76054ba23d8aba15a3.water.jpg_200x200_d7a548c3.jpg',
          title: '福建天门山',
          desc: '福建省福州市永泰县'
        }
      ]
    }
  }
}
</script>

<style lang=stylus scoped>
  @import '../../../assets/styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    display: flex
    height : 1.9rem
    overflow: hidden
    .item-img
      width : 1.7rem
      height : 1.7rem
      padding : .1rem
    .item-info
      flex: 1
      padding : .1rem
      min-width : 0
      .item-title
        line-height : .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height : .4rem
        font-size: .28rem
        color : #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
