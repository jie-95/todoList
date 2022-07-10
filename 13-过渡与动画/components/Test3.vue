!
<template>
  <div>
    <button @click="isShow = !isShow">显示/隐藏</button>
    <transition-group 
    appear
    name="animate__animated animate__bounce " 
    enter-active-class="animate__backInLeft"
    leave-active-class="animate__backOutLeft"
    >
      <h1 v-show="isShow" key="1">Hello!Mr.Shu</h1>
      <h1 v-show="isShow" key="2">Mr.Shu</h1>
    </transition-group>
  </div>
</template>

<script>
import "animate.css";
export default {
  name: "isShow",
  data() {
    return {
      isShow: true,
    };
  },
};
</script>

<style scoped>
h1 {
  background-color: orange;
  /* transition: 1s linear; */
}
</style>
