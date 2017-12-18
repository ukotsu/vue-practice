<template>
  <div class="l-wrapper">
    <MyHeader/>

    <main>
      <div class="p-mv">
        <div class="p-mv__inner">
          <h1 class="p-mv__copy">{{msg}}</h1>
        </div>
      </div>
      <div class="p-main-content">

        <section class="p-section">
          <h2 class="p-section__ttl">アコーディオン</h2>
          <div class="p-section__body">
            <MyAccordion/>
            <MyAccordionLoop/>
          </div>
        </section>

        <section class="p-section">
          <h2 class="p-section__ttl">タブ切り替えのやつ</h2>
          <div class="p-section__body">
            <MyTabContents/>
          </div>
        </section>

        <section class="p-section">
          <h2 class="p-section__ttl">スムーススクロール</h2>
          <div class="p-section__body">
            <MySmoothScroll/>
          </div>
        </section>

        <section class="p-section">
          <h2 class="p-section__ttl">モーダル</h2>
          <div class="p-section__body">
            <MyModal/>
          </div>
        </section>

      </div>
    </main>
    <MyFooter class="l-wrapper__footer" />
  </div>
</template>

<script>

import MyHeader from '@/components/MyHeader'
import MyFooter from '@/components/MyFooter'
import MyAccordion from '@/components/MyAccordion'
import MyAccordionLoop from '@/components/MyAccordionLoop'
import MyTabContents from '@/components/MyTabContents'
import MySmoothScroll from '@/components/MySmoothScroll'
import MyModal from '@/components/MyModal'

export default {
  data () {
    return {
      // msg: 'jQueryでやってたやつをVue.jsでやる'
      msg: 'ho'
    }
  },
  title: 'Home',
  components: {
    MyHeader,
    MyFooter,
    MyAccordion,
    MyAccordionLoop,
    MyTabContents,
    MySmoothScroll,
    MyModal
  }
}
</script>

<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';
.l-wrapper {
  min-height: 100vh;
  background: #fff;
  display: flex;
  flex-direction: column;
  &__footer {
    margin-top: auto;
  }
}
.p-mv {
  background: #d5d5d5;
  &__inner {
    @include maxWidth($width-default);
    height: 300px;
    margin: 0 auto;
    display: flex;
    align-items: center;
  }
  &__copy {
    @include fontSize(3);
    font-weight: bold;
    letter-spacing: 0.1em;
  }
}
.p-main-content {
  @include maxWidth($width-default);
  margin: 0 auto;
  padding-top: 60px;
  padding-bottom: 60px;
  > * ~ * {
    margin-top: 100px;
  }
}

.p-section {
  &__ttl {
    @include fontSize(1.8);

    font-weight: bold;
    margin-bottom: 2em;
    letter-spacing: 0.05em;
    &:after {
      content: '';
      display: block;
      color: #fff;
      width: 100%;
      height: 10px;
      background-color: lighten($color-theme, 45%);
      margin-top: 10px;
      background-image: linear-gradient(
        -45deg,
        currentColor 25%,
        transparent 0,
        transparent 50%,
        currentColor 0,
        currentColor 75%,
        transparent 0,
        transparent
      );
      background-size: 14px 14px;
    }
  }
  &__body {
    > * ~ * {
      margin-top: 1em;
    }
  }
}
</style>
