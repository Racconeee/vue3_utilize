<template>
  <q-dialog v-bind="$attrs" @hide="onHide">
    <q-card :style="{ width: '660px' }">
      <q-toolbar>
        <q-toolbar-title> 글쓰기</q-toolbar-title>
        <q-btn v-close-popup flat dense icon="close"></q-btn>
      </q-toolbar>
      <q-separator></q-separator>

      <PostForm
        v-model:title="form.title"
        v-model:category="form.category"
        v-model:content="form.content"
      ></PostForm>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { ref } from "vue";
import PostForm from "./PostForm.vue";

const form = ref(getInitialForm());

const onHide = () => {
  form.value = getInitialForm();
};

// import { getCategories } from "src/services/category";

// const categories = getCategories();

// const removeTag = () => {
//   console.log("removeTag");
// };

// const tagField = ref({});
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
