<template>
  <div>
    <ul class="p-tab-menu">
      <li v-for="item in list" @click="changeTab(item.id)" :class="{'is-active':active(item.id)}">{{ item.label }}</li>
    </ul>
    <div class="p-tab-body">
      <transition>
        <div v-for="item in list" :key="item.id" v-if="active(item.id)">
          <p>{{ item.content }}</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      current: 1,
      list: [{
        id: 1,
        label: 'menu1',
        content: 'コンテンツその1'
      }, {
        id: 2,
        label: 'menu2',
        content: 'コンテンツその2'
      }, {
        id: 3,
        label: 'menu3',
        content: 'コンテンツその3'
      }]
    }
  },
  methods: {
    active: function (id) {
      return this.current === id
    },
    changeTab: function (id) {
      this.current = id
    }
  }
}
</script>


<style lang="scss" scoped>
@import '../style/_variables.scss';
@import '../style/_mixin.scss';

.p-tab-menu {
  display: flex;
  li {
    padding: 1em 2em;
    background: #f5f5f5;
    border-radius: 4px 4px 0 0;
    @include transition(background);
    cursor: pointer;
    &.is-active {
      background: lighten($color-theme, 45%);
    }
    &:hover {
      color: $color-theme;
    }
  }
  li ~ li {
    margin-left: 0.5em;
  }
}
.p-tab-body {
  padding: 2em;
  border: 2px solid lighten($color-theme, 45%);
  overflow: hidden;
}

.v-enter-active,
.v-leave-active {
  @include transition(all);
}

.v-leave-active {
  position: absolute;
}

.v-enter {
  transform: translateX(-20px);
  opacity: 0;
}

.v-leave-to {
  transform: translateY(20px);
  opacity: 0;
}
</style>
