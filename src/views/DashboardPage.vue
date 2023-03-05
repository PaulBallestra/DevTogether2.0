<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Dashboard</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Dashboard</ion-title>
        </ion-toolbar>
      </ion-header>

      <Dashboard></Dashboard>

    </ion-content>
  </ion-page>
</template>

<script>
  import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
  import Dashboard from '../components/Dashboard.vue';

  export default {
    name: 'DashboardPage',
    components:{
      IonPage, IonHeader, IonToolbar, IonTitle, IonContent, Dashboard
    },
  }

</script>
