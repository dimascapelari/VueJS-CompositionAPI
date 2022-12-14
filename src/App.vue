<template>
  <AppProduct />
  <hr />

  First Name: {{ user.first_name }} (está reativo)<br />
  Last Name: {{ user.last_name }} (está reativo)<br />
  <hr />
  Admin First: {{ admin.first_name }} (está reativo)<br />
  Admin Last: {{ admin.last_name }} (está reativo)<br />
  <hr />
  Name: {{ name }} (não está reativo) <br /><br />

  <img @click="changeName()" alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import AppProduct from "./components/Products/AppProduct.vue";
// import { reactive } from "@vue/reactivity";
import { reactive, ref } from "vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    AppProduct,
  },

  setup() {
    const user = reactive({
      first_name: "Dimas",
      last_name: "Capelari",
    });

    const admin = ref({
      first_name: "Admin",
      last_name: "Master",
    });

    let name = "Dimas";
    const changeName = () => {
      name = "Capelari";
      // alert("chegou");
      user.first_name = "Maria Luiza";
      user.last_name = "Moioli Capelari";
      admin.value.first_name = "XXXX";
      admin.value.last_name = "YYYY";
    };

    return {
      admin,
      user,
      name,
      changeName,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
