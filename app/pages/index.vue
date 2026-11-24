<template>
  <div>
    <!-- メイン画像 -->
    <img
      :src="response.details.ext_1.url"
      :alt="response.details.ext_1.desc"
      width="800"
    >

    <!-- 業務紹介 -->
    <h1>{{ response.details.ext_2 }}</h1>

    <!-- コンテンツ説明 -->
    <p>{{ response.details.ext_3 }}</p>

    <!-- サービス情報 -->
    <h2>{{ response.details.ext_4.ext_4 }}</h2>
    <p>{{ response.details.ext_4.ext_5 }}</p>
  </div>
</template>

<script setup>
const config = useRuntimeConfig();

const { data: response } = await useFetch(
  `${config.public.apiBase}/rcms-api/2/service/3`,
  {
    credentials: 'include',
  }
);
</script>