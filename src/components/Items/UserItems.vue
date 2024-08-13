<template>
  <div class="user_block block">
    <div v-if="selectedUserItemsIds.length" class="selected_user_items">
      <div
        class="item"
        @click="unselectUserItem(item.id)"
        v-for="item in filteredSelectedUserItems"
      >
        {{ item.name }}
      </div>
      <div class="selected_counter">
        <span v-if="selectedUserItemsIds.length">{{
          `Selected ${selectedUserItemsIds.length} / ${userItems.length}`
        }}</span>
      </div>
    </div>
    <h2 v-else>No items selected</h2>
    <div class="user_items items">
      <div
        class="item"
        @click="selectUserItem(item.id)"
        v-for="item in userItems"
      >
        {{ item.name }}
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";
import { userItems } from "./const";
const selectedUserItemsIds = ref<number[]>([]);
const selectUserItem = (id: number) => {
  if (!selectedUserItemsIds.value.includes(id)) {
    selectedUserItemsIds.value.push(id);
    console.log("item selectedd");
  }
};
const unselectUserItem = (id: number) => {
  const index = selectedUserItemsIds.value.indexOf(id);
  if (index !== -1) {
    selectedUserItemsIds.value.splice(index, 1);
  }
};
const filteredSelectedUserItems = computed(() => {
  return userItems.filter((el) => selectedUserItemsIds.value.includes(el.id));
});

</script>

<style scoped></style>
