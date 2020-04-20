<template>
  <div class="container">
      <article class="post">
        <header class="post__header">
          <h1>ライフサイクルフック</h1>
        </header>
        <div class="post__main">



        </div>
      </article>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '~/components/Header.vue'


export default {
  components: {
    Header
  },
  data() {
    return {
      userName: {
        familyName: '田中',
        givenName: '1234'
      }
    }
  }
}
</script>

<style lang="scss">
.post {
  &__header {

  }
}
</style>
