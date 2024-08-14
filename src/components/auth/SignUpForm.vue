<template>
  <div>
    <div class="text-h5 text-center text-weight-bold q-mb-xl">회원가입</div>

    <q-form class="q-gutter-y-md">
      <q-input placeholder="닉네임" outlined dense></q-input>
      <q-input placeholder="이메일" outlined dense></q-input>
      <q-input
        placeholder="비밀번호(문자, 숫자조합 8자 이상)"
        outlined
        dense
      ></q-input>
      <div>
        <q-btn
          label="가입하기"
          class="full-width"
          unelebated
          color="primary"
          @click="$emit('changeView', 'SignUpForm')"
        ></q-btn>
        <div class="flex justify-between"></div>
      </div>
      <q-btn
        label="로그인 하기"
        unelevated
        flat
        color="black"
        class="full-width"
        @click="$emit('changeView', 'SignInForm')"
      ></q-btn>
    </q-form>
  </div>
</template>

<script setup>
defineEmits(["changeView"]);
</script>

<style lang="scss" scoped></style>
