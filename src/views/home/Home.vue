// BEM命名规则
// block__element--Modifier
<template>
    <div class="wrapper">
        <StaticPart />
        <Nearby />
    </div>
    <Docker />
</template>

<script>
import StaticPart from "@/views/home/StaticPart.vue";
import Nearby from "@/views/home/Nearby.vue";
import Docker from "@/views/home/Docker.vue";

export default {
    name: "HomeView",
    components: {Docker, Nearby, StaticPart}
}
</script>

<style lang="scss" scoped>

.wrapper {
  overflow-y:auto ;
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem .2rem .18rem;
}

</style>

