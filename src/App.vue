<template>
  <div id="app">
    <input type="text" v-model="message" />
    {{ message }}
    <div v-if="show == true">Vue.js.EP1</div>
    <div v-else>Vue.js EP2</div>
    <!-- valiable, index -->
    <div v-for="(animal, i) in animals" :key="i">
      {{ animal }}
    </div>
    <button v-on:click="submit()">click</button>
    {{ message }}
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "",
      show: true,
      animals: ["cat", "dog", "ant"],
    };
  },
  methods: {
    submit() {
      this.message = "Make Web Bkk";
      //console.log("Make Web BigThaiFlute");
    },
  },
};
</script>

<style scoped>
</style>
