<template>
  <div class="login">
        <label for="username">Username: </label>
        <input v-bind:value="username" v-on:input="onUsernameInput" name="username" id="username">
        <br><br>
        <label for="password">Password: </label>
        <input v-bind:value="password" v-on:input="onPasswordInput" name="password" id="password">
        <br><br>
        <button v-on:click="onLogin" onclick=onLogin()>Login</button>
        <br><br>
        <div v-if="success" id="success">Success!</div>
        <div v-else id="fail">Incorrect!</div>
  </div>

  
</template>

<script>
export default {
  name: 'LoginComponent',
  props: {
  },
  data () {
        return{
            username: "",
            password: "",
            success: false
        }
  },
  methods: {
    onUsernameInput(e){
        this.username = e.target.value;
    },
    onPasswordInput(e){
        this.password = e.target.value;
    },
    onLogin(){
        if (this.username === "jpazos" && this.password == "jpazos123"){
            this.success = true;
        }
        else{
            this.success = false;
        }

    }
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    #success {
        color: greenyellow;
    }
    #fail{
        color: red
    }
</style>
