<template>
  <h3 class="line-title">
    <img src="../assets/left.png">
    <div class="center">{{title}}</div>
    <img src="../assets/right.png">
  </h3>
</template>
<script>
export default {
  props: ['title']
}
</script>
<style lang="less">
.line-title {
  display: flex;
  justify-content: center;
  align-items: center;
  .center {
    padding: 0px 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #06D1F1
  }
}
</style>

