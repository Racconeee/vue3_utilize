<template>
  <StickySideBar>
    <q-card flat bordered>
      <q-list bordered separator>
        <q-item clickable v-ripple :active="true">
          <q-item-section>전체</q-item-section>
        </q-item>
        <q-item
          v-for="category in categories"
          :key="category.value"
          clickable
          v-ripple
        >
          <q-item-section>{{ category.label }}</q-item-section>
        </q-item>
      </q-list>
    </q-card>
  </StickySideBar>
</template>

<script setup>
import StickySideBar from "src/components/apps/post/StickySideBar.vue";
import { getCategories } from "src/services/category";

const categories = getCategories();
</script>

<style lang="scss" scoped></style>
