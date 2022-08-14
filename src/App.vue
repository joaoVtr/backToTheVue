<template>
  <TheHeader v-show="showHeader" />
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <div>
    Two-way data bind
    <br />
    <input v-model="name" type="text" />
    <br />
    <span v-text="name"> </span>
  </div>
  <br />

  <div>
    <div>On CLick</div>
    <button @click="test = 'ola Mundo'">Enviar</button>
    <div @mouseenter="test = ''">
      {{ test }}
    </div>
  </div>
  <br />
  <div>
    <div>Computed Properties</div>
    <div>{{ user.name }} {{ user.last_name }}</div>
    <div>{{ fullName }}</div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import TheHeader from "./components/TheHeader.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    TheHeader,
  },
  data() {
    return {
      showHeader: true,
      name: "joao",
      test: "",
      user: {
        name: "joao",
        last_name: "vitor",
      },
    };
  },
  computed: {
    fullName() {
      return this.user.name + " " + this.user.last_name + " computed";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
