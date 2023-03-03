<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Login</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Login</ion-title>
        </ion-toolbar>
      </ion-header>

      <div style="background-color: #1F1F1F; padding: 36px; border-radius: 5px; margin: 64px auto; max-width: 520px; display: flex; flex-direction: column; justify-content: center; gap: 36px;">

        <ion-input id="inputUsername" type="text" placeholder="Username" style="color: white; border-bottom: 1px solid gray;"></ion-input>
        <ion-input id="inputPassword" type="text" placeholder="Password" style="color: white; border-bottom: 1px solid gray;"></ion-input>
        <ion-button @click="login">LOGIN</ion-button>

        <ion-label id="labelResponse" style="text-align: center;"></ion-label>

      </div>

    </ion-content>
  </ion-page>
</template>

<script>

  import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonInput, IonButton, IonLabel } from '@ionic/vue';
  import axios from "axios";

  let axiosResponse = null

  axios.get('https://randomuser.me/api/').then((response) => {
    axiosResponse = response
    console.log(response.data.results[0].login)
  })

  export default{
    name: 'LoginPage',
    components: {
      IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonInput, IonButton, IonLabel
    },
    methods: {
      
      login: function(e){

        e.preventDefault()

        const inputUsername = document.getElementById('inputUsername').value
        const inputPassword = document.getElementById('inputPassword').value
        const labelResponse = document.getElementById('labelResponse')

        if(axiosResponse.data.results[0].login.username === inputUsername && axiosResponse.data.results[0].login.password === inputPassword){
          labelResponse.innerHTML = 'CONNECTED'
        }else{
          labelResponse.innerHTML = 'ERROR'
        }
      }
    }
  }

</script>
