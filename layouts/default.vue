<template>
  <div>
    <Header />
    <main>
      <nuxt />
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  },
}
</script>
