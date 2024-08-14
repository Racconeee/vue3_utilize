<template>
  <div>
    <div class="text-h4">Home</div>

    <section class="q-gutter-y-sm q-mt-lg">
      <q-card v-for="id in 100" :key="id">
        <q-card-section>{{ id }} 번째 게시글 </q-card-section>
      </q-card>
    </section>
  </div>
</template>

<script setup>
// 스크립트 코드가 여기에 들어갑니다.
</script>

<style lang="scss" scoped>
/* 스타일 코드가 여기에 들어갑니다. */
</style>

<route lang="yaml">
name: home-page
meta:
  requiresAuth: true
  width: 600px
</route>
