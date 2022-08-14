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
  <br /><br />

  <div>
    <div>On CLick</div>
    <button @click="test = 'ola Mundo'">Enviar</button>
    <div @mouseenter="test = ''">
      {{ test }}
    </div>
  </div>
  <br />
  <br />
  <div>
    <div>Computed Properties</div>
    <div>{{ user.name }} {{ user.last_name }}</div>
    <div>{{ fullName }}</div>
  </div>
  <br /><br />
  <div>
    Observadores
    <br />
    <input type="text" v-model="observer" /><br />
    {{ observer }}
    <br />
    <input type="text" v-model="objTest.name" />
    <br />
    <input type="text" v-model="objTest.second" />
    <br />
    {{ objTest }}
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
      observer: "euu",

      objTest: {
        name: "joao",
        second: "vitor",
      },
    };
  },
  computed: {
    fullName() {
      return this.user.name + " " + this.user.last_name + " computed";
    },
  },
  watch: {
    observer(newV, oldV) {
      this.consoleTest(newV, oldV);
    },
    objTest: {
      handler() {
        console.log("testObj alterado");
      },
      deep: true,
    },
  },
  methods: {
    consoleTest(newV, oldV) {
      console.log(this.observer, oldV);
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
