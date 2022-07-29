<template>
  <h1>
    HELLO
  </h1>
  <table>
    <tr v-for="items in list">
      <!-- <div>
        <table>
          <colgroup>
            <col>
            <img v-bind:src="items.avatar" :alt="`${name}`" />
            <col>
            <div>
              <div>{{ items.name }}</div>
              <div>{{ items.job }}</div>
            </div>
          </colgroup>
        </table>
      </div> -->
      <div>
        <div>
          <img v-bind:src="items.avatar" :alt="`${name}`" />
        </div>
        <div>
          <div>{{ items.name }}</div>
          <div>{{ items.job }}</div>
        </div>

      </div>
      <!-- {{ item.avatar }} -->

    </tr>
  </table>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Vue from 'vue'
// import axios from 'axios'
// import VueAxios from 'vue-axios'
// Vue.use(VueAxios,axios)
export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      list: []
    }
  },
  async created() {
    // this.list = [{ "name": "ram" }]
    // const data = Vue.axios.get('http://dummy.restapiexample.com/api/v1/employees').then((disp) => {
    //   console.log(disp)
    // })
    const response = await fetch("https://62e3dff33c89b95396d2a865.mockapi.io/users");
    const data2 = await response.json();
    console.log(data2)
    this.list = data2;
  }
}
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
