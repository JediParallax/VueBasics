<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h3>Hello World</h3>
    <form action="" class="routers">
      <router-link to="/test" msg="Hello! I'm a foreigner variable! (:">test</router-link>
      <router-link to="/">user</router-link>
    </form>
    <router-view msg="Hello! I'm a foreigner variable! (:"></router-view>
  </div>
</template>

<script>

import test from "./components/test.vue";
import user from "./components/user.vue";

export default {
  name: 'App',
  components: {
   test,
   user
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  background-color: rgb(71, 95, 121);
  color:  rgb(186, 221, 205);
  
}

.component-division{
    border: 3px solid rgb(40, 46, 43);
}

li{
    list-style: none;
}

a{
  background-color:   rgb(71, 95, 121);
  border: 3px solid rgb(117, 223, 175); 
  color:  rgb(117, 223, 175);
  padding: 5px;
  text-decoration: none;
}

a:hover{
  background-color: rgb(117, 223, 175);
  border: 3px solid rgb(71, 95, 121); 
  color:  rgb(71, 95, 121);    
}

form.routers{
  margin: 20px;
}

button{
  margin: 6px;
}


</style>
