<script>
export default {
  name: "LifeComponent",
  methods: {
    btnAdd: function () {
      this.count++;
    },
  },
  data() {
    return {
      count: 0,
    };
  },
  // 커모넌트 라이프 사이클 함수 (Hook)
  beforeCreate: function () {
    console.log("beforeCreate...1");
  },
  created: function () {
    console.log("created...1");
  },
  beforeMount: function () {
    console.log("beforeMount...1");
  },
  mounted: function () {
    console.log("mounted...1");
  },
  beforeUpdate: function () {
    console.log("beforeUpdate...1");
  },
  updated: function () {
    console.log("updated...1");
  },
  beforeUnmount: function () {
    console.log("beforeUnmount...1");
  },
  unmounted: function () {
    console.log("console...1");
  },
};
</script>
<template>
  <h4>LifeComponent</h4>
  <p>
    카운터 : {{ count }}
    <button @click="btnAdd">증가</button>
  </p>
</template>
<style scoped></style>
