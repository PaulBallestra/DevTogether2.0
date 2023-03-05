<template>

    <div id="container">

        <ion-input class="input" id="inputUsername" type="text" placeholder="Username"></ion-input>
        <ion-input class="input" id="inputPassword" type="password" placeholder="Password"></ion-input>
        <ion-button @click="login">LOGIN</ion-button>

        <ion-label id="labelResponse"></ion-label>

    </div>

</template>

<script>

    import { IonInput, IonButton, IonLabel } from '@ionic/vue';
    import { defineComponent } from 'vue';
    import axios from "axios";

    let axiosResponse = null

    axios.get('https://randomuser.me/api/').then((response) => {
        axiosResponse = response
        console.log(response.data.results[0].login)
    });

    export default defineComponent({
        name: 'Login',
        components: {
            IonInput, IonButton, IonLabel
        },
        methods: {
            login: function(e){
                e.preventDefault()

                const inputUsername = document.getElementById('inputUsername').value
                const inputPassword = document.getElementById('inputPassword').value
                const labelResponse = document.getElementById('labelResponse')

                axiosResponse.data.results[0].login.username === inputUsername && axiosResponse.data.results[0].login.password === inputPassword ? labelResponse.innerHTML = 'CONNECTED' : labelResponse.innerHTML = 'ERROR'
            }
        }
    });

</script>

<style scoped>

    #container{
        background-color: #1F1F1F; 
        padding: 36px; 
        border-radius: 5px; 
        margin: 64px auto; 
        max-width: 520px; 
        display: flex; 
        flex-direction: column; 
        justify-content: center; 
        gap: 36px;
    }

    .input{
        color: white; 
        border-bottom: 1px solid gray;
    }

    .input::after{
        color: red;
    }

    #labelResponse{
        text-align: center;
    }

</style>