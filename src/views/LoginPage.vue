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

      <Login></Login>
      
    </ion-content>
  </ion-page>
</template>

<script>

  import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
  import Login from '../components/Login.vue'
  
  export default{
    name: 'LoginPage',
    components: {
      IonPage, IonHeader, IonToolbar, IonTitle, IonContent, Login
    },
  }

</script>
