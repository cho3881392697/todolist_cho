<script setup>
import { ref } from "vue";
const todoitems = ref([
  { name: "英語第一", time: "5/19 8:50", done: false, ignore: false },
  { name: "立志リライト", time: "5/19 23:59", done: false, ignore: false },
]);
const newItemName = ref("");
const newItemTime = ref(0);
const addItem = () => {
  todoitems.value.push({
    name: newItemName.value,
    time: newItemTime.value,
    done: false,
    ignore: false,
  });
};
</script>

<template>
  <div>
    <div>ToDolist</div>
    <div v-for="item in todoitems" :key="item.name">
      <div v-if="!item.ignore" class="ige">
        <div v-if="!item.done" class="todoitem">
          <div class="name">名前: {{ item.name }}</div>
          <div class="time">{{ item.time }} まで</div>
          <button @click="item.done = true">done</button>
          <button @click="item.ignore = true">del</button>
        </div>
      </div>
    </div>
    <div>
      <label>
        名前
        <input v-model="newItemName" type="text" />
      </label>
      <label>
        期限
        <input v-model="newItemTime" type="test" />
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
  <div>
    <br />
    <div>Donelist</div>
    <div v-for="item in todoitems" :key="item.name">
      <div v-if="!item.ignore" class="ige">
        <div v-if="item.done" class="doneitem">
          <div class="name">名前: {{ item.name }}</div>
          <div class="time">{{ item.time }} まで</div>
          <button @click="item.done = false">not yet</button>
          <button @click="item.ignore = true">del</button>
        </div>
      </div>
    </div>
  </div>
</template>
<style></style>
