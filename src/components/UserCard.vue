<template>
  <div class="conatiner">
    <div class="user-card">
      <h1>Научу зарабатывать от 50 000р. в час</h1>
      <div class="main-information flex">
        <img src="../assets/couch.jpg" width="500px" />
        <div class="info">
          <h2>{{ getAuthorFullName }}</h2>
          <strong>Бизнес-коуч</strong>
          <ul class="list">
            <li>Учу делать РЕАЛЬНЫЕ бабки, на себя просто не хватило времени</li>
            <li>НЕ знаю, что такое "Успешный Успех", но знаю, что нужно ТЕБЕ!</li>
            <li>Пообещал, что побреюсь, когда кого-нибудь ОБМАНУ.</li>
          </ul>
        </div>
      </div>
      <p>Участников: {{ users.length }}</p>
      <ul class="list">
        <li v-for="(user, index) in users" :key="index">
          {{ `${index + 1} ${getFullUserName(user)}` }} // Список Участников
        </li>
      </ul>
      <button type="button" @click="currentPage--">Пред.</button>
      <button type="button" v-for="page in pages" :key="page" @click="currentPage = page">
        {{ page }}
      </button>
      <button type="button" @click="currentPage++">След.</button>
      <p>Страница: {{ currentPage }} из {{ pages }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserCard",
  data() {
    return {
      firstName: "Игнатий",
      secondName: "Илларионович",
      lastName: "Богатов",
      users: [
        {
          firstName: "Иван",
          secondName: "Иванов",
          lastName: "Иванович",
        },
        {
          firstName: "Пётр",
          secondName: "Петрович",
          lastName: "Петров",
        },
        {
          firstName: "Василий",
          secondName: "Васильевич",
          lastName: "Василенко",
        },
      ],
      pages: 3,
      currentPage: 1,
    };
  },
  computed: {
    getAuthorFullName() {
      return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase();
    },
  },
  methods: {
    getFullUserName(user) {
      return `${user.firstName} ${user.secondName} ${user.lastName}`.toUpperCase();
    },
    loadUsers(page) {
      console.log("Загрузка пользователей... страница - " + page);
    },
  }, // Методы работают также, но являются более трудоёмкими чем computed Если операция сложная то лучше использовать computed, но в computed мы не можем передавать аргументы а в методах можем
  watch: {
    currentPage(page) {
      this.loadUsers(page);
    },
  },
};
</script>

<style lang="scss" scoped>
.flex {
  display: flex;
  gap: 15px;
  div {
    padding: 20px;
    border: 1px solid rgb(212, 212, 175);
  }
}
ul {
  padding: 0;
  margin: 0;
  padding-left: 12px;
  margin-bottom: 24px;
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
</style>
