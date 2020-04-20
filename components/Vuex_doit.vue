<template>
  <div>
    <article class="post">
      <header class="post__header">
        <h1>Vuex実践</h1>
      </header>
      <div class="post__main">
<pre v-highlightjs>
<code class="javascript">[path] /bbmembers/store/index.js
</code></pre>
<pre v-highlightjs>
<code class="javascript">export const state = () => ({
  categoryID:undefined,
})
export const mutations = {
  changeCategoryID (state, value) {
    state.categoryID = value;
  },
}
</code></pre>









<pre v-highlightjs>
<code class="javascript">[path] /bbmembers/pages/index.vue
</code></pre>
<pre v-highlightjs>
<code class="javascript">//65行目あたり
watch: {
  async categoryID (val, old) {
    let data = await dataGet(1, val);
    this.currentPage = data.currentPage;
    this.lastPage = data.lastPage;
    this.userdata = data.userdata;
  }
},
</code></pre>
<pre v-highlightjs>
<code class="javascript">//82行目あたり
async asyncData ({ query, store }) {
  let data = await dataGet(query.page, store.state.categoryID);
  return {
    currentPage : data.currentPage,
    lastPage : data.lastPage,
    userdata : data.userdata
  };
},
</code></pre>

      </div>
    </article>
  </div>
</template>
<script lang="ts">
import Vue, { PropOptions } from 'vue'
import hljs from 'highlight.js'

export default Vue.extend({
  data() {
    return {
    }
  },
  computed: {
  },
  updated() {
    hljs.initHighlighting();
  },
})
</script>

<style lang="scss">
.post {
  margin-bottom: 5em;
  &__header {
    background: #F4F4F4;
    border-radius: 8px;
    padding: 1.2em 2.2em;
    h1 {
      font-weight: 800;
      font-size: 2.5rem;
    }
  }
  &__main {
    margin: 2em 0;
	  font-size: 1.6rem;
    h2 {
      font-size: 2.2rem;
      font-weight: 600;
      margin: 1em 0;
    }
    h3 {
      font-size: 2.0rem;
      font-weight: 600;
      margin: 0.8em 0;
    }
    p {
      margin: 1em 0;
    }
  }
  pre {
    margin: 1em 0;
    padding: 0;
  }
}
</style>
