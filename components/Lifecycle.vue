<template>
  <div>
    <article class="post">
      <header class="post__header">
        <h1>ライフサイクルフック</h1>
      </header>
      <div class="post__main">
        <h2>ライフサイクルフックとは</h2>
        <p>状態が変わった時に実行されるフック関数。</p>
        <pre v-highlightjs>
<code class="javascript">async asyncData (context) {
    let result = await axios.get(`http://0.0.0.0:3000/api/user/all`);
    return {
      jsondata : result.data.users
    };
},
</code></pre>
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
    asyncData() {
    },
    fetch() {
    },
    beforeCreate() {
    },
    created() {
    },
    beforeMount() {
    },
    mounted() {
    },
    beforeUpdate() {
    },
    updated() {
    },
    beforeDestroy() {
    },
    destroyed() {
    },
  }
&lt;/script&gt;
</code></pre>
        <h3>nuxtServerInit</h3>
        <p>SSRでストア内のアクションにて定義されている場合。<br>
        サーバーサイドからクライアントサイドにデータを渡すことができる。<br>
        fetchとの違いは、middlewareよりも前で、すべてのページに適応される。</p>
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
