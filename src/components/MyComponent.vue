<template>
  <div class="root">
    <div class="email">
      <h1>{{ text }}</h1>
      <label for="">
        Введите email
        <input type="text" :value="email" @input="emailInput($event.target.value)" />
      </label>
      <label for="">
        Введите пароль
        <input type="password" :value="password" @input="passwordInput($event.target.value)" />
      </label>

      <p>Емейл: {{ email }}</p>
      <p>Пароль: {{ password }}</p>
    </div>

    <div class="counter">
      <button @click="dicrement">-</button>
      <input type="number" :value="numValue" :min="minValue" :max="maxValue" @input="numInput($event.target.value)" />
      <button @click="increment">+</button>
      {{ numValue }}
    </div>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      text: "Привет VUE!",
      email: "naterid@yandex.ru",
      password: "qwerty222",
      numValue: 1,
      maxValue: 10,
      minValue: 1,
    };
  },
  methods: {
    emailInput(value) {
      this.email = value;
    },
    passwordInput(value) {
      this.password = value;
    },
    numInput(value) {
      this.numValue = value;
    },
    increment() {
      if (this.numValue < this.maxValue) {
        this.numValue++;
      }
    },
    dicrement() {
      if (this.numValue > this.minValue) {
        this.numValue--;
      }
    },
  },
};
</script>
