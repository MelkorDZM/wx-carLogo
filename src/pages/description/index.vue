<template>
  <div class="des">
      1.此小程序用来计算和统计路上骑车品牌占比 <br>
      2.数据结果仅代表用户当地情况，不代表市场总体品牌比例 <br>
      3.数据使用权及归属权均属于用户
      4.原则上只统计私家车品牌，不包括出租车（大众的太多了）
      5.用户在收集，采集数据时，<a>注意安全！</a>
  </div>
</template>

<script>

export default {
  data () {
    return {

    }
  }
}
</script>

<style lang="scss" rel="stylesheet/scss" scoped>

    .des{
        color: #333;
        font-size:16px;
        line-height:1.7;
        padding:20px;
    }

    a{
        display: inline;
        color: red;
    }

</style>
