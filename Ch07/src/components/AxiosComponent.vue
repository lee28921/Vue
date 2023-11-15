<script setup>
import axios from "axios";
import { ref, reactive } from "vue";
const users = ref([]);
const inputTxt = ref("");
const user = reactive({
  data: {},
});

const btnGetUser = () => {
  axios({
    url: "http://localhost:8080/Ch10/user1",
    method: "get",
    responseType: "json",
  })
    .then((response) => {
      console.log(response);
      users.value = response.data;
    })
    .catch((err) => {});
};

const btnGetUserById = async () => {
  // axios(async - await)
  // - 비동기방식을 동기방식 스타일로 표기
  // - 실제 동작은 비동기방식으로 처리
  const response = await axios.get(
    "http://localhost:8080/Ch10/user1/" + inputTxt.value
  );
  console.log(response);
  user.data = response.data;
};

const registerUser = () => {
  console.log(user);
  axios
    .post("http://localhost:8080/Ch10/user1", user)
    .then((response) => {
      console.log(response);
      alert("등록!");
    })
    .catch((err) => {
      console.log(err);
    });
};
const updateUser = () => {
  console.log(user);
  axios
    .put("http://localhost:8080/Ch10/user1", user)
    .then((response) => {
      console.log(response);
      alert("수정!");
    })
    .catch((err) => {
      console.log(err);
    });
};
const btnDeleteUser = () => {
  axios
    .delete(`http://localhost:8080/Ch10/user1/${inputTxt.value}`)
    .then((response) => {
      console.log(response);
      alert("수정!");
    })
    .catch((err) => {
      console.log(err);
    });
};
</script>

<template>
  <h4>Axios 실습</h4>
  <button @click="btnGetUser">User 요청</button>
  <table border="1">
    <tr>
      <th>아이디</th>
      <th>이름</th>
      <th>나이</th>
      <th>주소</th>
    </tr>
    <tr v-for="member in users">
      <td>{{ member.uid }}</td>
      <td>{{ member.name }}</td>
      <td>{{ member.age }}</td>
      <td>{{ member.addr }}</td>
    </tr>
  </table>

  <h4>Get</h4>
  <input type="text" v-model="inputTxt" />
  <button @click="btnGetUserById">User 요청</button>
  <table border="1">
    <tr>
      <th>아이디</th>
      <th>이름</th>
      <th>나이</th>
      <th>주소</th>
    </tr>
    <tr>
      <td>{{ user.data.uid }}</td>
      <td>{{ user.data.name }}</td>
      <td>{{ user.data.age }}</td>
      <td>{{ user.data.addr }}</td>
    </tr>
  </table>

  <h4>POST</h4>
  <form @submit.prevent="registerUser">
    <table border="1">
      <tr>
        <td>아이디</td>
        <td><input type="text" v-model="user.uid" /></td>
      </tr>
      <tr>
        <td>이름</td>
        <td><input type="text" v-model="user.name" /></td>
      </tr>
      <tr>
        <td>나이</td>
        <td><input type="text" v-model="user.age" /></td>
      </tr>
      <tr>
        <td>주소</td>
        <td><input type="text" v-model="user.addr" /></td>
      </tr>
      <input type="submit" value="등록" />
    </table>
  </form>

  <h4>PUT</h4>
  <form @submit.prevent="updateUser">
    <table border="1">
      <tr>
        <td>아이디</td>
        <td><input type="text" v-model="user.uid" /></td>
      </tr>
      <tr>
        <td>이름</td>
        <td><input type="text" v-model="user.name" /></td>
      </tr>
      <tr>
        <td>나이</td>
        <td><input type="text" v-model="user.age" /></td>
      </tr>
      <tr>
        <td>주소</td>
        <td><input type="text" v-model="user.addr" /></td>
      </tr>
      <input type="submit" value="수정" />
    </table>
  </form>
  <h4>DELETE</h4>
  <input type="text" v-model="inputTxt" />
  <button @click="btnDeleteUser">삭제</button>
</template>

<style scoped></style>
