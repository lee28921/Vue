<script setup>
import MyComponent1 from "./components/MyComponent1.vue";
import MyComponent2 from "./components/MyComponent2.vue";
import MyComponent3 from "./components/MyComponent3.vue";
import OptionComponent1 from "./components/OptionComponent1.vue";
import OptionComponent2 from "./components/OptionComponent2.vue";
import OptionComponent3 from "./components/OptionComponent3.vue";
</script>

<template>
  <h3>Ch03 컴포넌트</h3>
  <h3>1) 컴포넌트</h3>
  <MyComponent1 />
  <MyComponent2 />
  <MyComponent3 />

  <h3>2) Options API</h3>
  <OptionComponent1 />
  <OptionComponent2 />
  <OptionComponent3 />

  <h3>3) 컴포넌트 통신</h3>
  <h3>4) 컴포넌트 생명주기</h3>
</template>

<style scoped></style>
