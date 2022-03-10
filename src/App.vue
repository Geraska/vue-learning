<template>
  <h2>App Component</h2>
  <UserList />
</template>

<style>
  @import "./style.css";
</style>

<script>
  import UserList from "./components/UserList.vue"
  
  export  default {
    name : "App",
    components : {
      UserList
    }
  }
</script>

