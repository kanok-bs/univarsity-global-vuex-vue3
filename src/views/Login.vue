<script setup lang="ts">
import { useRouter } from "vue-router";
import { useStore } from "vuex";
const store = useStore();
const router = useRouter();
const Login = () => {
  store.dispatch("ADD_AUTHENTICATE_STATUS", true);
  router.push({ name: "Home" });
};
</script>

<template>
  <div>
    <form @submit.prevent="Login">
      <div class="container">
        <label for="uname"><b>Username</b></label>
        <input type="text" placeholder="Enter Username" name="uname" />
        <label for="psw"><b>Password</b></label>
        <input type="password" placeholder="Enter Password" name="psw" />
        <button type="submit">Login</button>
      </div>
    </form>
  </div>
</template>
<style scoped>

.container{
  left: 20%;
  right: 20%;
  position: absolute;
}

input[type="text"],
input[type="password"] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  box-sizing: border-box;
}

button {
  background-color: #04aa6d;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
}

button:hover {
  opacity: 0.8;
}

.cancelbtn {
  width: auto;
  padding: 10px 18px;
  background-color: #f44336;
}

.imgcontainer {
  text-align: center;
  margin: 24px 0 12px 0;
}

img.avatar {
  width: 40%;
  border-radius: 50%;
}

.container {
  padding: 16px;
}

span.psw {
  float: right;
  padding-top: 16px;
}
</style>
