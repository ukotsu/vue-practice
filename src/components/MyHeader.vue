<template>
  <header class="p-header">
    <div class="p-header__inner">
      <router-link to="/" class="p-header__logo">LOGO</router-link>
      <MyGlobalNavi/>
    </div>
  </header>
</template>

<script>
import MyGlobalNavi from '@/components/MyGlobalNavi'

export default {
  data () {
    return {
      msg: 'ヘッダーだぜ'
    }
  },
  components: {
    MyGlobalNavi
  }
}
</script>


<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';

.p-header {
  background: #f5f5f5;
  border-bottom: 2px solid $color-theme;
  &__inner {
    @include maxWidth($width-default);
    margin: 0 auto;
    height: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__logo {
    text-decoration: none;
  }
}
</style>
