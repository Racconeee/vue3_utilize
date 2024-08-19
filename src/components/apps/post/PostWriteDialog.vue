<template>
  <q-dialog v-bind="$attrs" @hide="onHide">
    <q-card :style="{ width: '660px' }">
      <q-toolbar>
        <q-toolbar-title> 글쓰기</q-toolbar-title>
        <q-btn v-close-popup flat dense icon="close"></q-btn>
      </q-toolbar>
      <q-separator></q-separator>

      <q-form class="q-pa-md q-gutter-y-sm">
        <q-input v-model="form.title" outlined placeholder="제목"> </q-input>
        <q-select
          v-model="form.category"
          outlined
          placeholder="카테고리"
          :options="categories"
        >
          <template v-if="!form.category" #selected>
            <span class="text-grey-7">카테고리를 선택하세요.</span>
          </template>
        </q-select>
        <q-input
          v-model="form.content"
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
      </q-form>
      <q-separator></q-separator>

      <q-card-actions align="right">
        <q-btn flat label="취소하기" v-close-popup />
        <q-btn type="submit" flat label="저장하기" color="primary" />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { ref } from "vue";
import { getCategories } from "src/services/category";

const categories = getCategories();

const form = ref(getInitialForm());

const removeTag = () => {
  console.log("removeTag");
};

const tagField = ref({});

const onHide = () => {
  form.value = getInitialForm();
  tagField.value = "";
};
</script>

<script>
const getInitialForm = () => ({
  title: "",
  category: "",
  content: "",
  tags: [],
});
</script>

<style lang="scss" scoped></style>
