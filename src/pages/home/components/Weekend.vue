<template>
<div>
  <div class="title">周末去哪儿</div>
  <ul>
    <li class="item boder-bottom" v-for="item of recommendList" :key="item.id">
      <div class="item-img-wrapper">
        <img class="item-img" :src="item.imgUrl"/>
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default{
  name: 'HomeWeekend',
  data: function () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/68/de862f94e383a6.jpg_r_640x214_f9df927b.jpg',
          title: '福州必游Top10',
          desc: '大美福州, 必游之处'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1509/b5/07bc81fc254ed6.jpg_r_640x214_8879c815.jpg',
          title: '土楼不能不说的秘密',
          desc: '一座座神秘的建筑，一段段传奇的历史'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/f6/82acfa5c7f472c.jpg_r_640x214_508da3cb.jpg',
          title: '熊孩子玩乐去哪儿',
          desc: '这里向熊孩子们招手'
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
    .item-img-wrapper
      overflow: hidden
      height : 0
      padding-bottom : 33.9%
      .item-img
        width : 100%
    .item-info
      padding : .1rem
      .item-title
        line-height : .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height : .4rem
        font-size: .28rem
        color : #ccc
        ellipsis()
</style>
