<template>
  <BaseCard class="q-pa-lg">
    <div class="flex">
      <q-btn
        icon="sym_o_arrow_back"
        flat
        round
        dense
        color="grey"
        size="16px"
      ></q-btn>
      <q-space></q-space>
      <q-btn
        icon="sym_o_favorite"
        flat
        round
        dense
        color="grey"
        size="16px"
      ></q-btn>
      <q-btn
        icon="sym_o_bookmark"
        flat
        round
        dense
        color="grey"
        size="16px"
      ></q-btn>
    </div>

    <div class="flex items-center">
      <q-avatar>
        <img src="https://cdn.quasar.dev/img/boy-avatar.png" alt="" />
      </q-avatar>
      <div class="q-ml-md">
        <div>combat</div>
        <div class="text-grey-6">3일전</div>
      </div>
      <q-space></q-space>
      <q-btn icon="more_horiz" round flat>
        <q-menu>
          <q-list style="min-width: 100px">
            <q-item clickable v-close-popup>
              <q-item-section>수정하기</q-item-section>
            </q-item>
            <q-item clickable v-close-popup>
              <q-item-section>삭제하기</q-item-section>
            </q-item>
          </q-list>
        </q-menu>
      </q-btn>
    </div>
    <div class="q-mt-md text-h5 text-weight-bold">제목입니다.</div>
    <div class="row items-center q-gutter-x-md q-mt-md justify-end">
      <PostIcon name="sym_o_visibility" label="1" tooltip="조회수"></PostIcon>
      <PostIcon name="sym_o_sms" label="2" tooltip="댓글"></PostIcon>
      <PostIcon name="sym_o_favorite" label="3" tooltip="좋아요"></PostIcon>
      <PostIcon name="sym_o_bookmark" label="4" tooltip="북마크"></PostIcon>
    </div>

    <q-separator class="q-my-lg"></q-separator>
    <div>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum ab,
      perferendis earum dignissimos iste maiores dolore quo praesentiumdicta
      nihil recusandae veniam dolorem officiis consequatur dolor ratione,
      adipisci reprehenderit dolorum. Lorem ipsum dolor sit amet consectetur
      adipisicing elit. Nostrum ab, perferendis earum dignissimos iste maiores
      dolore quo praesentiumdicta nihil recusandae veniam dolorem officiis
      consequatur dolor ratione, adipisci reprehenderit dolorum. Lorem ipsum
      dolor sit amet consectetur adipisicing elit. Nostrum ab, perferendis earum
      dignissimos iste maiores dolore quo praesentiumdicta nihil recusandae
      veniam dolorem officiis consequatur dolor ratione, adipisci reprehenderit
      dolorum.
    </div>
  </BaseCard>
</template>

<script setup>
import PostIcon from "src/components/apps/post/PostIcon.vue";
import BaseCard from "src/components/base/BaseCard.vue";
</script>

<style lang="scss" scoped>
/* 스타일 코드가 여기에 들어갑니다. */
</style>
