<script setup>
import { reactive } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();

const user = reactive({
  name: "",
  age: 0,
  addr: "",
});
const SubmitHandler = () => {
  // router 인스턴스로 컴포넌트 라우팅(데이터 포함)
  router.push({ name: "FormResult2", params: user });
};
</script>
<template>
  <h4>Form2</h4>

  <form @submit.prevent="SubmitHandler">
    <input type="text" v-model="user.name" /> <br />
    <input type="number" v-model="user.age" /> <br />
    <select v-model="user.addr">
      <option>서울</option>
      <option>대전</option>
      <option>대구</option>
      <option>부산</option>
      <option>광주</option>
    </select>
    <br />
    <input type="submit" value="전송" />
  </form>
</template>
<style scoped></style>
