<template>
  <div class="selection_block block">
    <div v-if="selectionItem" class="selected_item_wrapper">
      <div class="item">
        {{ selectionItem?.name }}
      </div>
    </div>
    <h2 v-else>No item is selected</h2>
    <div class="selection_items items">
      <div
        class="item"
        @click="makeSelection(item.id)"
        v-for="item in selectionItems"
      >
        {{ item.name }}
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { selectionItems } from "./const";
import type { ItemType } from "./types";
const selectionItem = ref<ItemType | undefined>();

const makeSelection = (id: number) => {
  if (selectionItem.value?.id !== id) {
    selectionItem.value = selectionItems?.find((el) => el.id === id);
  }
};
</script>

<style scoped></style>
