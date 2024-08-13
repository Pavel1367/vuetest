<template>
  <main>
    <div class="container">
      <UserItems />
      <SelectionItems />
    </div>
  </main>
</template>

<script setup lang="ts">
import SelectionItems from "./SelectionItems.vue";
import UserItems from "./UserItems.vue";
</script>

<style>
.selected_item_wrapper {
  height: 240px;
  width: 100%;
}
.selected_item_wrapper .item {
  height: 100%;
  max-width: 300px;
  margin-left: auto;
}
.items {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.selected_user_items {
  min-height: 220px;
  max-width: 300px;
  border: 1px solid black;
  padding: 10px;
  gap: 10px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
.selected_counter {
  grid-column: 1/-1;
  margin-top: auto;
}

.item {
  text-align: center;
  padding: 5px;
  border: 1px solid black;
  cursor: pointer;
}
.block {
  padding: 30px;
  flex-direction: column;
  flex: 1;
  height: 1000px;
  border: 1px solid black;
  display: flex;
  gap: 40px;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  gap: 20px;
}
</style>
