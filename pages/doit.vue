<template>
  <div class="container">
    <div>
      <Lifecycle />
      <Routing />
      <Vuex />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '~/components/Header.vue'
import Lifecycle from '~/components/Lifecycle_doit.vue'
import Routing from '~/components/Routing_doit.vue'
import Vuex from '~/components/Vuex_doit.vue'


export default {
  components: {
    Header,
    Lifecycle,
    Routing,
    Vuex,
  },
  data() {
    return {
      userName: {
      }
    }
  },

}
</script>
