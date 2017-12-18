<template>
  <div>
    <p>モーダルを開く</p>
    <div>
      <p>モーダルコンテント</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isShow: false
    }
  }
}
</script>


<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';

</style>
