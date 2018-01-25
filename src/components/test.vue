<template>
    <div class="component-division">
        <h1>Hola Vida</h1>
        <hr>
        <span v-if="mood">
            <p v-html="happy"></p>
            <hr>
        </span>
        <span v-else>
            <p v-html="sad"></p>
            <hr>
        </span>
        <ul>
            <li>{{user.name}}</li>
            <li>{{user.lastName}}</li>
            <li v-for=" task in stuff">
                {{task.title}}
            </li>
        </ul>
        <hr>
       <input class="testInputs" type="text" v-model="user.name" @keyup.74="jMonitor" @keyup.9="tabMonitor">
       <input class="testInputs" type="text" v-model="user.lastName" @keyup.74="jMonitor">
       <button class="testButtons" type="button" v-on:click="saludar(user.name, user.lastName)">click me</button>
       <hr>
        <button class="testButtons" @click.left="left()" @click.middle="middle()" @click.right="right()" id="foreigner">{{msg}}</button>

    </div>
    
</template>

<script>
export default {
  name: "test",
  data() {
    return {
      happy: "<i>Ohio! minna-san</i>",
      sad: "<i>just kill me quick, please</i>",
      mood: true,
      user: {
        name: "",
        lastName: ""
      },
      stuff: [
        { title: "hello 10.5 hours" },
        { title: "staying in 5 hours" },
        { title: "sleep 6 hours" }
      ]
    };
  },

  methods: {
      saludar(name, lastname){
         var names = confirm("hello "+name +", is your Lastname "+lastname +"?");
         (names) ? alert("yayyy") : alert("aw, snap!");
      },
      jMonitor(){
          alert("La letra J esta prohibida, por favor no la pongas");
      },
      tabMonitor(){
          alert("don't be so lazy! don't use tab!");
      },
      right(){
          alert("Right click? seriously?");
      },
     middle(){
          alert('who the hell uses the middle click? you weirdo!');
      },
      left(){
          alert('excellent choise, if you want to remain the same forevar...try using another buttons of your mouse, geez..');
      },

},
  props: {
        msg: {
            type: String
        }
      }
  
};
</script>

<style>

    button.testButtons{
        background-color: rgb(71, 95, 121);
        border: 3px solid #41B883;
        color: #41B883;
    }

    button#foreigner:hover{
        background-color: #41B883;
        border: 3px solid #35495E;
        color:#35495E;   
        font-family:'Times New Roman', Times, serif;
        font-weight: bold;
    }

     #foreigner{
        padding: .5rem;
        margin-bottom: .57rem;
    }

    .testInputs {
        background-color: rgb(218, 240, 230);
        border: 3px solid #41B883;
    }

   
</style>


