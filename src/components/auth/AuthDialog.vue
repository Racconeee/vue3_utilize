<template>
  <q-dialog
    :model-Value="modelValue"
    @update:model-Value="(val) => $emit('update:modelValue', val)"
    transition-show="none"
    transition-hide="none"
  >
    <q-card :style="{ width: '400px' }">
      <q-card-section class="flex justify-end">
        <q-btn icon="close" flat round dense v-close-popup></q-btn>
      </q-card-section>

      <q-card-section class="q-px-xl q-pb-xl">
        <SignInForm
          v-if="viewMode === 'SignInForm'"
          @change-view="changViewMode"
        />
        <SignUpForm
          v-else-if="viewMode === 'SignUpForm'"
          @change-view="changViewMode"
        />
        <FindPasswordForm
          v-else
          @change-view="changViewMode"
        ></FindPasswordForm>
      </q-card-section>
    </q-card>
  </q-dialog>
</template>
<!-- v-model 의 값이 true 면 열리고 false 면 닫히는 구조
하지만 이값 을 이 컴포넌트 밖에서 조절해서 열리고 닫고를 조절할 수 있다. -->
<script setup>
import { ref } from "vue";
import FindPasswordForm from "./FindPasswordForm.vue";
import SignInForm from "./SignInForm.vue";
import SignUpForm from "./SignUpForm.vue";

defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
});

defineEmits(["update:modelValue"]);

const viewMode = ref("SignInForm");
const changViewMode = (mode) => (viewMode.value = mode);
</script>

<style lang="scss" scoped></style>
