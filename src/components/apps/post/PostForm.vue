<template>
  <q-form>
    <q-card-section class="q-pa-md q-gutter-y-sm">
      <q-input v-model="titleModel" outlined placeholder="제목"> </q-input>
      <q-select
        v-model="categoryModel"
        outlined
        placeholder="카테고리"
        :options="categories"
        emit-value
        map-options
      >
        <template v-if="!categoryModel" #selected>
          <span class="text-grey-7">카테고리를 선택하세요.</span>
        </template>
      </q-select>
      <q-input
        v-model="contentModel"
        type="textarea"
        outlined
        placeholder="내용을 작성해주세요"
      ></q-input>
      <q-input
        v-model="tagField"
        outlined
        placeholder="태그를 입력해주세요~! (입력 후 Enter)"
        prefix="#"
      ></q-input>
      <q-chip outline dense color="teal" removable @remove="removeTag">
        vue.js</q-chip
      >
    </q-card-section>
    <q-separator></q-separator>

    <q-card-actions align="right">
      <slot name="actions">
        <q-btn flat label="취소하기" v-close-popup />
        <q-btn type="submit" flat label="저장하기" color="primary" />
      </slot>
    </q-card-actions>
  </q-form>
</template>

<script setup>
import { ref, computed } from "vue";

import { getCategories } from "src/services/category";

const props = defineProps({
  title: {
    type: String,
  },
  category: {
    type: String,
  },
  content: {
    type: String,
  },
  tage: {
    type: Array,
    default: () => [],
  },
});

const removeTag = () => {
  console.log("removeTag");
};

const tagField = ref({});

const emit = defineEmits([
  "update:title",
  "update:category",
  "update:content",
  "update:tags",
]);

const titleModel = computed({
  get: () => props.title,
  set: (val) => emit("update:title", val),
});

const categoryModel = computed({
  get: () => props.category,
  set: (val) => emit("update:category", val),
});

const contentModel = computed({
  get: () => props.content,
  set: (val) => emit("update:content", val),
});
const categories = getCategories();
</script>

<style lang="scss" scoped></style>
