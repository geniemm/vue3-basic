<template>
  <AppHeader v-bind:appTitle="message" v-on:change="changeMassage"> </AppHeader>
</template>

<script>
// import 컴포넌트이름 from './컴포넌트 경로'
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    // '컴포넌트이름' : 컴포넌트 내용
    //AppHeader: AppHeader,
    // 앞과 뒤가 같으면 줄어든다(키:밸류)
    AppHeader,
  },
  data() {
    return {
      message: "앱 헤더 컴포넌트",
    };
  },
  methods: {
    changeMassage() {
      this.message = "변경됨";
    },
  },
};
</script>

<style scoped></style>
