<template>
  <table>
    <tr v-for="items in list">
      <div className="card">
        <div>
          <img v-bind:src="items.avatar" :alt="`${name}`" className="imageContainer" />
        </div>
        <div className="cardBody">

          <div className="nameContainer">{{ items.name }}
          </div>

          <div className="jobContainer">{{ items.job }}
          </div>

        </div>
      </div>

    </tr>
  </table>
</template>

<script>

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

.card {
  border-radius: 20px;
  border: 1px solid;
  display: flex;
  flex-direction: row;
  padding: 20px;
  margin-bottom: 20px;
  width: 500px;
}

.imageContainer {
  border-radius: 50%;
  width: 100px;
}

.cardBody {
  display: flex;
  flex-direction: column;
  padding-left: 20px;
}

.nameContainer {
  text-align: left;
  font-size: 35px;
  font-weight: bold;
}

.jobContainer {
  text-align: left;
  font-size: 20px;
}
</style>
