<template>
  <nav>
    <ul class="p-gnavi">
      <li>
        <router-link to="/about/">About</router-link>
      </li>
      <li>
        <router-link to="/contact/">Contact</router-link>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
@import '../style/_variables.scss';

.p-gnavi {
  display: flex;
  li ~ li {
    margin-left: 2em;
  }
  a {
    text-decoration: none;
  }
}
</style>
