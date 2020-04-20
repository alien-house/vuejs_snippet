<template>
  <div>
    <article class="post">
      <header class="post__header">
        <h1>ルーティング</h1>
      </header>
      <div class="post__main">
        <h2>ライフサイクルフックとは</h2>
        <p>状態が変わった時に実行されるフック関数。</p>
        <h3>nuxtServerInit</h3>
        <p>SSRでストア内のアクションにて定義されている場合。<br>
        サーバーサイドからクライアントサイドにデータを渡すことができる。<br>
        fetchとの違いは、middlewareよりも前で、すべてのページに適応される。</p>
        <pre v-highlightjs>
<code class="html">&lt;template&gt;
	&lt;div id=&quot;app&quot;&gt;
	&lt;/div&gt;
&lt;/template&gt;
&lt;script&gt;
  export default {
    validate() {
      return true
    },
  }
&lt;/script&gt;
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
      margin: 0.5em 0;
    }
    h3 {
      font-size: 2.0rem;
      font-weight: 600;
      margin: 0.5em 0;
    }
  }
}
</style>
