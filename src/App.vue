<template>
  <div id="app">
    <button
      @click="komponentСhoice(component)"
      v-for="component in components"
      :key="component.id"
    >
      {{ component }}
    </button>
    <div class="components">
      <komponentBlue v-if="flag === 'componentBlue'" />
      <KomponentPink v-if="flag === 'componentPink'"></KomponentPink>
      <KomponentYellow v-if="flag === 'componentYellow'"></KomponentYellow>
    </div>
  </div>
</template>

<script>
import KomponentYellow from "./components/komponentYellow";
import KomponentPink from "./components/komponentPink";
import komponentBlue from "./components/komponentBlue";
export default {
  name: "App",
  components: {
    KomponentYellow,
    KomponentPink,
    komponentBlue,
  },

  data() {
    return {
      components: ["componentBlue", "componentPink", "componentYellow"],
      flag: "componentBlue",
    };
  },

  methods: {
    komponentСhoice(nameComponent) {
      this.flag = nameComponent;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.components {
  display: flex;
  justify-content: center;
  margin-top: 60px;
}
</style>
