<script setup></script>
<template>
  <h4>Parent</h4>
  <p>
    <router-link to="/parent/child1">child1</router-link>&nbsp;
    <router-link to="/parent/child2">child2</router-link>&nbsp;
  </p>

  <router-view></router-view>
</template>
<style scoped></style>
