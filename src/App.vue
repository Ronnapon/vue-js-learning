<template>
  <div id="app">
    <table>
      <tr>
        <h1 v-if="level == 1">Register</h1>
      </tr>
      <tr>
        <td width>Username</td>
        <td><input type="text" v-model="username" /></td>
        {{
          username
        }}
      </tr>
      <tr>
        <td>Password</td>
        <td><input type="password" v-model="password" /></td>
        {{
          password
        }}
      </tr>
      <br />
      <tr>
        <button v-on:click="submit()">Submit</button>
        <button v-on:click="clear()">Clear</button>
        <div v-if="show == true">บันทึกเรียบร้อยแล้ว</div>
      </tr>
    </table>
    <table>
      <br /><br />
      <tr>
        <td>
          <div v-if="show == true">
            ข้อมูลสัตว์
            <div v-for="(animal, i) in animals" :key="i">
              {{ animal }}
            </div>
          </div>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      level: "1",
      username: "",
      password: "",
      message: "",
      show: false,
      animals: ["cat", "dog", "ant"],
    };
  },
  methods: {
    submit() {
      this.message = "บันทึกเรียบร้อยแล้ว";
      this.show = true;
    },
    clear() {
      this.username = "";
      this.password = "";
      this.message = "";
      this.show = false;
    },
  },
};
</script>

<style scoped>
</style>
