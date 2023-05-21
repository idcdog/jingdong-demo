<template>
    <div class="position">
        <span class="iconfont position__icon">&#xe61f;</span>
        北京理工大学国防科技园2号楼10层
        <span class="iconfont position__notice">&#xe601;</span>
    </div>
    <div class="search">
        <span class="iconfont">&#xe6ac;</span>
        <span class="search__text">山姆会员商店优惠商品</span>
    </div>
    <div class="banner">
        <img class="banner__img" src="http://www.dell-lee.com/imgs/vue3/banner.jpg" />
    </div>
    <div class="icons">
        <div v-for="icon in iconList" :key="icon.imgName" class="icons__item">
            <img :src="`http://www.dell-lee.com/imgs/vue3/${icon.imgName}.png`" :alt="icon.desc" class="icons__item__img">
            <p class="icons__item__desc">{{icon.desc}}</p>
        </div>
    </div>
    <div class="gap"></div>
</template>

<script lang="js">
export default {
    name: "StaticPart",
    setup(){
        const iconList=[
            {imgName: '超市', desc: '超市便利'},
            {imgName: '菜市场', desc: '菜市场'},
            {imgName: '水果店', desc: '水果店'},
            {imgName: '鲜花', desc: '鲜花绿植'},
            {imgName: '医药健康', desc: '医药健康'},
            {imgName: '家居', desc: '家居时尚'},
            {imgName: '蛋糕', desc: '烘培蛋糕'},
            {imgName: '签到', desc: '签到'},
            {imgName: '大牌免运', desc: '大牌免运'},
            {imgName: '红包', desc: '红包套餐'}
        ]
        return {iconList}
    }
}
</script>
// scoped 用于限制css作用范围, 表示当前定义的样式只对当前组件中有效果, 对外部没有影响
<style lang="scss" scoped>
@import "../../style/viriables.scss";
@import "../../style/mixins.scss";
.position{
  @include ellipsis;
  color:$content-fontcolor;
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  .position__icon{
    position: relative;
    top: .01rem;
    font-size: .2rem;
  }
  .position__notice{
    position: absolute;
    right: 0;
    top: .17rem;
    font-size: .2rem;
  }
}
.search {
  margin-bottom: .12rem;
  vertical-align: middle;
  height: .32rem;
  line-height: .32rem;
  background: #F5F5F5;
  color: #B7B7B7;
  border-radius: .16rem;
  .iconfont{
    display: inline-block;
    font-size: .18rem;
    position: relative;
    top: .01rem;
    padding: 0 .12rem 0 .16rem;
  }
  &__text{
    display: inline-block;
    font-size: .14rem;
  }
}
.banner{
  height: 0;
  overflow: hidden;
  // 这里用了一个技巧, 防止图片加载后下方内容出现抖动
  // 表示元素的底部内边距（padding）的值为其父元素宽度的 25.4%。内边距是指元素内容与元素边框之间的空间
  padding-bottom: 25.4%;
  &__img{
    width: 100%;
  }
}
.icons{
  display: flex;
  flex-wrap: wrap;
  margin-top: .16rem;

  &__item{
    width: 20%;
    &__img{
      display: block;
      width: .4rem;
      height: .4rem;
      margin: 0 auto;
    }
    &__desc{
      text-align: center;
      margin: .06rem 0 .16rem 0;
      color: $content-fontcolor;
    }
  }
}
.gap{
  height: .1rem;
  background: $content-bgcolor;
  margin: 0 -.18rem;
}
</style>
