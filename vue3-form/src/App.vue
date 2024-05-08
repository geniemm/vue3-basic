<template>
  <form action="" @:submit.prevent="submitForm">
    <!-- v-on -->
    <div>
      <label for="userId">ID: </label>
      <input id="userId" type="text" v-model="username" />
    </div>
    <div>
      <label for="password">PW: </label>
      <input type="text" v-model="password" />
    </div>
    <button type="submit">로그인</button>
  </form>
</template>

<script>
import axios from "axios";
import { ref } from "vue";
export default {
  setup() {
    // data와 완전하게 동일하다.
    var username = ref("");
    var password = ref("");

    // methods
    var submitForm = () => {
      axios
        .post("https://jsonplaceholder.typicode.com/users/", {
          username: username.value,
          password: password.value,
        })
        .then((Response) => {
          console.log(Response);
        });
    };
    return { username, password, submitForm };
  },

  // methods:{
  //   logText(){
  //     this.password
  //   }
  // }

  // data() {
  //   return {
  //     username: "",
  //     password: "",
  //   };
  // },
  // methods: {
  //   submitForm() {
  //     // event.preventDefault();
  //     const data = {
  //       username: this.username,
  //       password: this.password,
  //     };
  //     axios
  //       .post("https://jsonplaceholder.typicode.com/users/", data)
  //       .then((Response) => {
  //         console.log(Response);
  //       });
  //     console.log("제출됨");
  //   },
  // },
};
</script>

<style scoped></style>
