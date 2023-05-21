<template>
    <div class="nearby">
        <h3 class="nearby__title">附近的店铺</h3>
        <div v-for="item in nearbyList" :key="item.id" class="nearby__item">
            <img :src="item.img" alt="nearby" class="nearby__item__img" />
            <div class="nearby__content">
                <div class="nearby__content__title">{{ item.title }}</div>
                <div class="nearby__content__tags">
                    <span
                        v-for="(innerItem,innerIndex) in item.tags"
                        :key="innerIndex"  class="nearby__content__tag">{{ innerItem }}
                    </span>
                </div>
                <p class="nearby__content__highlight">{{ item.desc }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Nearby",
    setup(){
        const nearbyList=[{
            id: '1',
            title: '沃尔玛',
            tags: ['月售1万+','起送¥0','基础运费¥5'],
            desc: 'VIP尊享满88元减4元运费券',
            img: 'http://www.dell-lee.com/imgs/vue3/near.png'
        },{
            id: '2',
            title: '沃尔玛',
            tags: ['月售1万+','起送¥0','基础运费¥50'],
            desc: 'VIP尊享满88元减4元运费券',
            img: 'http://www.dell-lee.com/imgs/vue3/near.png'
        }]
        return {nearbyList}
    }
}
</script>
<style lang="scss" scoped>
@import "../../style/viriables.scss";
@import "../../style/mixins.scss";
.nearby{
  &__title{
    margin: .16rem 0 .02rem 0;
    font-size: .18rem;
    font-weight: normal;
    color: $content-fontcolor;
  }
  &__item{
    padding-top: .12rem;
    display: flex;
    &__img{
      margin-right: .16rem;
      width: .56rem;
      height: .56rem;
    }
  }
  &__content{
    flex: 1;
    padding-bottom: .12rem;
    border-bottom: 1px solid $content-bgcolor;

    &__title{
      line-height: .22rem;
      font-size: .16rem;
      color: $content-fontcolor;
    }
    &__tags{
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
      margin-top: .08rem;
    }
    &__tag{
      margin-right: .16rem;
    }
    &__highlight{
      color: #E93B3B;
      margin: .08rem 0 0 0;
      line-height: .18rem;
      font-size: .13rem;
    }
  }
}
</style>
