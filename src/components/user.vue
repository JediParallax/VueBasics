<template>
    <div class="component-division users"> 
        <h1>User Component</h1>
        <ul>
            <li v-for="user in users" >
                {{user.name}} - {{user.email}}
                <button class="userButtons" @click="deleteUser()">x</button>
            </li>
        </ul>
        <form @submit.prevent="addUser()">
            <input class="userInputs" type="text" v-model="newUser.name" placeholder="Nombre">
            <input class="userInputs" type="email" v-model="newUser.email" placeholder="email">
            <button class="userButtons" type="submit">add</button>
        </form>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                users: [
                    
                ],

                newUser: {}
            }
        },

        methods: {

            addUser(){
             this.users.push(this.newUser);
             this.newUser = {};
            },
            deleteUser(user){
                this.users.splice(this.users.indexOf(user), 1);
            }
        },

        created() {
            this.$http.get('https://jsonplaceholder.typicode.com/users')
            .then(res => this.users = res.body);
        }

    }
</script>

<style scoped>
    .users{
        background-color: rgb(117, 223, 175);
        color: rgb(71, 95, 121);
        padding: 1.7rem;
    }

    button.userButtons{
        background-color: rgb(117, 223, 175);
        border: 3px solid rgb(71, 95, 121); 
        color:  rgb(71, 95, 121); 
    }

    button.userButtons:hover{
        background-color:   rgb(71, 95, 121);
        border: 3px solid rgb(117, 223, 175); 
        color:  rgb(117, 223, 175);
    }

    input.userInputs{
        background-color: rgb(218, 240, 230);
        border: 3px solid rgb(71, 95, 121); 
    }

</style>