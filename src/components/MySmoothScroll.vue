<template>
  <div>
    <ul class="p-menu">
      <li><a href="#" v-scroll-to="'#box1'">ボックス1へ ▼</a></li>
      <li><a href="#" v-scroll-to="'#box2'">ボックス2へ ▼</a></li>
      <li><a href="#" v-scroll-to="{el: '#box3', offset: this.offset}">ボックス3へ ▼</a></li>
    </ul>
    <div id="box1" class="p-box">
      <p><a href="https://github.com/rigor789/vue-scrollto" target="_blank" rel="noopener noreferrer">vue-scrollto</a> を使っています。<br>仕組みは現在位置から指定要素までの差を <i>window.requestAnimationFrame</i> で描画しているみたいです。</p>
    </div>
    <div id="box2" class="p-box">
      <p>トップへ戻るボタンも同様に実装できます。</p>
      <p><a href="#" v-scroll-to="{el: 'body'}">▲ トップへ戻る</a></p>
    </div>
    <div id="box3" class="p-box p-box--border-top">
      <p>オフセットも対応しているので、レスポンシブとか、ヘッダーが途中から固定になるとかの時も対応できそうです。</p>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import VueScrollTo from 'vue-scrollto'
Vue.use(VueScrollTo, {
  duration: 1000,
  easing: [0.23, 1, 0.32, 1]
})

export default {
  data () {
    return {
      isShow: false,
      offset: 60
    }
  }
}
</script>


<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';
.p-menu{
  display: flex;
  margin-bottom: 2em;
  > li~ li{
    margin-left: 1em;
  }
  a{
    text-decoration: none;
    padding: 1em 2em;
    background: lighten($color-theme, 50%);
    border-radius: 4px;
    @include transition(background);
    display: block;
    &:hover{
      background: lighten($color-theme, 45%);
    }
  }
}

.p-box{
  border: 2px solid lighten($color-theme, 45%);
  padding: 4em;
  & ~ &{
    margin-top: 4em;
  }
  &--border-top{
    border-top-width: 60px;
  }
}

</style>
