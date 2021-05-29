<template>
  <div>
    <!-- トップコンテンツ -->
    <section class="jumbotron text-center">
      <div class="container">
        <h1 class="jumbotron-heading">データ分析基礎</h1>
        <p class="lead text-muted">
          Python を用いたデータ分析
        </p>
        <p>
          <a href="https://www.python.org/" class="btn btn-primary my-2">
            Python
          </a>
        </p>
      </div>
    </section>
    <main>
      <div class="album py-5">
        <div class="container">
          <div class="row">
            <!-- 商品カード -->
            <ProductCard
              v-for="(product, index) in products"
              :key="index"
              :name="product.name"
              :img="product.img"
              :text="product.text"
              :url="products.url"
            />
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
  // axios モジュールから読み込み
  import axios from 'axios'

  export default {
    //非同期処理を同期処理にするために async で宣言
    async asyncData() {
      // Stein の API URL / シート名
      const url =
        'https://api.steinhq.com/v1/storages/60b278fdd2a8585c5af28178/product'
      // API のレスポンス
      // await でレスポンスが返ってくるまで待機
      // 商品データの取得
      const { data } = await axios.get(url)
      return { products: data }
    },
  }
</script>