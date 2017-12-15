<template>
  <footer class="p-footer">
    <div class="p-footer__inner">
      <p class="p-copyright">&copy; Junya Tanigaki</p>
    </div>
  </footer>
</template>

<script>
import MyGlobalNavi from '@/components/MyGlobalNavi'

export default {
  data () {
    return {
      msg: ''
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

.p-footer {
  background: $color-theme;
  &__inner {
    @include maxWidth($width-default);
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    margin: 0 auto;
  }
}
.p-copyright {
  // text-align: right;
  color: #fff;
  @include fontSize(1);
}
</style>
