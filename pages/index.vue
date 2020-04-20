<template>
  <div class="container">
    <div>
      <Lifecycle />
      <Routing />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Lifecycle from '~/components/Lifecycle.vue'
import Routing from '~/components/Routing.vue'
import Header from '~/components/Header.vue'


export default {
  components: {
    Header,
    Lifecycle,
    Routing,
  },
  data() {
    return {
      userName: {
      }
    }
  },
  validate() {
    console.log("validate");
    return true
  },
  asyncData() {
    console.log("asyncData");
  },
  fetch() {
    console.log("fetch");
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    console.log("mountesd");
  },
  beforeUpdate() {
    console.log("beforeUpdate");
  },
  updated() {
    console.log("updated");
  },
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
}
</script>
