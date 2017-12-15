<template>
  <div>
    <dl class="p-accordion">
      <dt class="p-accordion__btn" @click="toggle" :class="{'is-active': isShow}">ボタンだよ</dt>
      <transition name="accordion" v-on:before-enter="onBeforeEnter" v-on:enter="onEnter" v-on:before-leave="onBeforeLeave" v-on:leave="onLeave">
        <dd class="p-accordion__body" v-show="isShow">
          <div class="p-accordion__content">
            <p>なかみだよ</p>
            <p>なかみだよ</p>
            <p>なかみだよ</p>
            <p>なかみだよ</p>
          </div>
        </dd>
      </transition>
    </dl>
  </div>
</template>

<script>

export default {
  data () {
    return {
      isShow: false
    }
  },
  methods: {
    toggle: function () {
      this.isShow = !this.isShow
    },
    onBeforeEnter: function (el) {
      el.style.height = 0
    },
    onEnter: function (el) {
      el.style.height = el.scrollHeight + 'px'
    },
    onBeforeLeave: function (el) {
      el.style.height = el.scrollHeight + 'px'
    },
    onLeave: function (el) {
      el.style.height = 0
    }
  }
}
</script>


<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';

.p-accordion {
  &__btn {
    @include fontSize(1.6);
    color: $color-theme;
    background: lighten($color-theme, 45%);
    padding: 1em;
    cursor: pointer;
    position: relative;

    &:after {
      content: '';
      border: solid transparent;
      border-width: 6px 4px 0 4px;
      border-top-color: $color-theme;
      position: absolute;
      right: 30px;
      top: calc(50% - 3px);
      @include transition(transform);
    }
    &.is-active {
      &:after {
        transform: rotateX(180deg);
      }
    }
  }
  &__body {
    background: #f5f5f5;
    overflow: hidden;
  }
  &__content {
    padding: 2em;
  }
}

.accordion-enter-active {
  transition: all 1s $ease-easeOut;
}
.accordion-leave-active {
  transition: all 1s $ease-easeOut;
}
</style>
