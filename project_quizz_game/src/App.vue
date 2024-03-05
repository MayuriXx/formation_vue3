<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="My first VueJS App"/> -->
  <div>
    <h1>Quizz Game</h1>
  </div>
  <input type="radio" name="options" value="True">
  <label>True</label><br>
  <input type="radio" name="options" value="False">
  <label>False</label><br>
  <button class="send" type="button">Submit</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  created() {
    // fetch('https://opentdb.com/api.php?amount=1&category=21')
    //   .then(response => response.json())
    //   .then(data => console.log(data));

    this.axios.get('https://opentdb.com/api.php?amount=1&category=21')
    .then((response) => {
      console.log(response.data)
    })
  }
}

//https://opentdb.com/api.php?amount=1&category=21 -> API
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
  max-width: 960px;
  
  input[type="radio"] {
    margin: 10px;
  }
  button.send {
    margin-top: 12px;
    height: 40px;
    min-width: 120px;
    padding: 0 16px;
    color: #fff;
    background-color: #1867c0;
    border: 1px solid #1867c0;
    cursor: pointer;
  }
}
</style>
