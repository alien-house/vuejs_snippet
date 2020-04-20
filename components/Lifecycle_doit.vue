<template>
  <div>
    <article class="post">
      <header class="post__header">
        <h1>ライフサイクルフック実践</h1>
      </header>
      <div class="post__main">
        <h2>dataGetメソッド</h2>
        <p>メンバーの一覧データを取得するメソッド。</p>
<pre v-highlightjs>
<code class="javascript">[path] /bbmembers/pages/index.vue
</code></pre>

<pre v-highlightjs>
<code class="javascript">/**
 * メンバーたちのデータ取得メソッド
 * パラメータによってカテゴリーフィルターが可能
 * @param qpage 現在のページ番号
 * @param categoryID カテゴリー名。デフォルト値はundefined
 */
async function dataGet(qpage = undefined, categoryID = undefined) {
  let page = (qpage != undefined && qpage != null) ? qpage : 1;
    return await client.getEntries({
      'content_type': 'member',
      "fields.categories.sys.contentType.sys.id": "category",
      "fields.categories.fields.title[all]": categoryID,
      order: '-sys.createdAt',
      limit: MAX_ENTRY,
      skip: MAX_ENTRY * (page - 1)
    })
    .then( (entry) => {
      let maxnum = Math.ceil(entry.total / MAX_ENTRY);
      return {
        currentPage : Number(page),
        lastPage : maxnum,
        userdata : entry.items
      };
    })
}
</code></pre>


        <h2>asyncData</h2>
        <p>サーバーサイドでデータを取得し、それをレンダリングしたい時に使用する。コンポーネントを初期化する前に非同期の処理を行えます。</p>
<pre v-highlightjs>
<code class="javascript">//75行目あたり
async asyncData () {
  let data = await dataGet();
  return {
    currentPage : data.currentPage,
    lastPage : data.lastPage,
    userdata : data.userdata
  };
}
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
