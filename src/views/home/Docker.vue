<template>
    <div class="docker">
        <div
            v-for="(item,index) of dockerList"
            :key="item.icon"
            :class="{'docker__item': true,'docker__item--active': index===0}"
            >
            <div class="iconfont" v-html="item.icon" />
            <div class="docker__title">{{item.text}}</div>
        </div>
    </div>
</template>
<script>
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Docker",
    setup(){
        const dockerList=[
            {icon: '&#xe61e;', text: '首页'},
            {icon: '&#xe7e5;', text: '购物车'},
            {icon: '&#xe600;', text: '订单'},
            {icon: '&#xe6b1;', text: '我的'}
        ];
        return {dockerList}
    }
}
</script>
<style lang="scss" scoped>
@import "../../style/viriables.scss";
@import "../../style/mixins.scss";
.docker {
  display: flex;
  box-sizing: border-box;
  position: absolute;
  color:$content-fontcolor;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border-top: 1px solid $content-bgcolor;
  padding: 0 .18rem;
  // & 表示外层修饰符, 此处就等同于.docker
  &__item {
    flex:1px;
    text-align: center;
    .iconfont {
      font-size: .18rem;
      margin: .07rem 0 .02rem 0;
    }
    // & 此处等同于.docker__item
    &--active{
      color: #1FA4FC;
    }
  }
  &__title{
    // 我们将字体设置为10px, 但是由于浏览器最小支持的字体大小是12px, 所以我们采用缩放形式实现
    font-size: .2rem;
    transform: scale(0.5,0.5);
    transform-origin: center top;
  }
}
</style>
