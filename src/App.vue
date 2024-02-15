<template>
  <div id="root">
    <!-- <my-component /> -->
    <Photoredactor />
    <!-- <UserCard /> -->
    <SearchUsers />
  </div>
</template>

<script>
// import MyComponent from "./components/MyComponent";
import Photoredactor from "./components/PhotoRedactor.vue";
import SearchUsers from "./components/SearchUsers.vue";
// import UserCard from "./components/UserCard";
export default {
  name: "App",
  components: {
    // MyComponent,
    Photoredactor,
    SearchUsers,
  },
};
</script>
