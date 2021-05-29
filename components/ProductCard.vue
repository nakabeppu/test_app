<template>
  <a class="col-md-4" :href="url" target="_blank">
    <div class="card mb-4 box-shadow">
      <img class="card-img-top" :src="img" data-holder-rendered="true" />
      <div class="card-body">
        <p class="card-text">{{ name }}</p>
        <div class="d-flex justify-content-between align-items-center">
          <small class="text-muted"> {{ text }} </small>
        </div>
      </div>
    </div>
  </a>
</template>

<script>
export default {
  // オブジェクト
  props: {
    name: {
      // 型
      type: String,
      // デフォルト値
      default: '',
    },
    img: {
      type: String,
      default: '',
    },
    text: {
      type: String,
      default: '',
    },
    url: {
      type: String,
      default: '',
    },
  },
}
</script>