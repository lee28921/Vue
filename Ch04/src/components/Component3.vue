<script setup>
import Component4 from "./Component4.vue";
import { provide } from "vue";

const user2 = {
  name: "홍길동",
  age: 23,
  addr: "부산",
};

provide("user2", user2);
</script>
<template>
  <h4>Component3</h4>
  <Component4 />
</template>
<style scoped></style>
