<template>
  <div class="container">
    <h1>Я найду тебя!</h1>
    <input type="text" :value="searchValue" @input="inputSearch($event.target.value)" />
    <ul>
      <li v-for="(user, index) in findUser" :key="index">{{ user }}</li>
    </ul>
    <p>Всего имён - {{ users.length }} , совпадений - {{ findUser.length }}</p>
  </div>
</template>

<script>
export default {
  name: "UserCard",
  data() {
    return {
      users: ["Евгений", "Алиса", "Данил", "Роман", "Алексей", "Владислав", "Владимир"],
      searchValue: "",
    };
  },
  computed: {
    findUser() {
      return this.users.filter((user) => user.toLowerCase().includes(this.searchValue.toLocaleLowerCase()));
    },
  },
  methods: {
    inputSearch(value) {
      this.searchValue = value;
      console.log(this.searchValue);
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
}
</style>
