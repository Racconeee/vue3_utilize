<template>
  <q-layout view="lHh Lpr lhh" class="bg-grey-2">
    <q-header bordered class="bg-white text-grey-9">
      <q-toolbar>
        <q-btn flat dense to="/">
          <q-toolbar-title>
            <q-avatar>
              <img src="/logo.png" />
            </q-avatar>
            피카츄
          </q-toolbar-title>
        </q-btn>
        <q-space></q-space>
        <q-btn stretch flat label="Home" to="/home" />
        <q-btn stretch flat label="수강하기" />
        <q-btn stretch flat label="온라인 강의 " />
        <q-btn stretch flat label="유튜브" />
        <q-separator class="q-my-md q-mr-md" vertical></q-separator>
        <q-btn
          unelevated
          rounded
          color="primary"
          @click="openAuthDialog"
          label="로그인/회원가입"
        ></q-btn>
      </q-toolbar>
    </q-header>

    <q-page-container :style="pageContainerStyles">
      <router-view />
    </q-page-container>
    <auth-dialog v-model="authDialog"></auth-dialog>
  </q-layout>
</template>

<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
import { ref } from "vue";

import AuthDialog from "src/components/auth/AuthDialog.vue";

const route = useRoute();
const pageContainerStyles = computed(() => ({
  maxWidth: route.meta?.width || "1080px",
  margin: "0 auto",
}));

const authDialog = ref(true);
const openAuthDialog = () => {
  authDialog.value = true;
};
</script>
