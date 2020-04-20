<template>
  <nav class="nav">
    <h1>Vue.jsスニペット</h1>
  </nav>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Header',
})
</script>
<style lang="scss">
.nav {
  padding: 2em 0;
  h1 {
    font-size: 2.4rem;
    font-weight: 900;
    letter-spacing: 1px;
    color: #1FB787;
    text-align: center;
  }
}
</style>
