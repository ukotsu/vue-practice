<template>
  <div>
    <MyHeader/>
    <div class="mv">
      <h1>{{msg}}</h1>
    </div>
  </div>
</template>

<script>

import MyHeader from '@/components/MyHeader'

export default {
  data () {
    return {
      msg: 'アバウトページ'
    }
  },
  title: 'About',
  components: {
    MyHeader
  }
}
</script>
