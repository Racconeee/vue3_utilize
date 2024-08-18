<template>
  <q-page padding>
    <div class="row q-col-gutter-x-lg">
      <PostLeftBar class="col-grow"></PostLeftBar>
      <section class="col-7">
        <PostHeader></PostHeader>
        <PostList :items="posts"></PostList>
      </section>
      <PostRightBar
        class="col-3"
        @open-write-dialog="openWriteDialog"
      ></PostRightBar>
    </div>
    <PostWriteDialog v-model="postDialog"></PostWriteDialog>
  </q-page>
</template>

<script setup>
import { useRouter } from "vue-router";
import PostList from "src/components/apps/post/PostList.vue";
import PostHeader from "./components/PostHeader.vue";
import PostLeftBar from "./components/PostLeftBar.vue";
import PostRightBar from "./components/PostRightBar.vue";
import { ref } from "vue";
import PostWriteDialog from "src/components/apps/post/PostWriteDialog.vue";

const router = useRouter;

const posts = Array.from(Array(20), (_, index) => ({
  id: index,
  title: "Vue3 Firebase  강좌" + index,
  content:
    "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reprehenderit necessitatibus voluptatum unde, temporibus debitis perspiciatis quos doloribus eaque nostrum, placeat veritatis voluptates quod ex laborum nulla hicaliquid assumenda laboriosam.",
  readCount: 1,
  commentCount: 2,
  likeCount: 3,
  bookmarkCount: 4,
  tags: ["html", "css", "javascript"],
  uid: "uid",
  category: "카테고리" + index,
}));
const postDialog = ref(false);
const openWriteDialog = () => {
  postDialog.value = true;
};
</script>

<style lang="scss" scoped></style>
