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

      <div style="background-color: #1F1F1F; padding: 36px; border-radius: 5px; margin: 64px auto 32px auto; max-width: 520px; display: flex; flex-direction: column; justify-content: center; gap: 36px;">

        <div style="margin: auto; width: 350px; height: 350px; background-color: white; position: relative;">

          <div id="compteur" style="position: absolute;">
            <ion-img src="assets/images/compteur_empty.png"></ion-img>
          </div>
          <div id="arrow" style="position: absolute;">
            <ion-img style="position: relative;" src="assets/images/compteur_arrow.png"></ion-img>
          </div>

        </div>
        <div style="margin: auto; display: flex; gap: 12px;">

          <ion-button @click="decrement">
            <ion-label>-</ion-label>
          </ion-button>

          <ion-label id="labelValue" style="margin: auto;">0</ion-label>

          <ion-button @click="increment">
            <ion-label>+</ion-label>
          </ion-button>

        </div>

      </div>

    </ion-content>
  </ion-page>
</template>

<script>
  import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonLabel, IonButton, IonImg } from '@ionic/vue';

  let value = 0

  export default {
    name: 'DashboardPage',
    components:{
      IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonLabel, IonButton, IonImg
    },
    methods: {

      increment: function(e){

        e.preventDefault()

        const labelValue = document.getElementById('labelValue')
        const arrow = document.getElementById('arrow')

        if(value !== 200)
          value++
        else
          value = 200

        labelValue.innerHTML = value

        arrow.style.transform = 'rotate('+value*1.18+'deg)'

      },

      decrement: function(e){
        e.preventDefault()

        const labelValue = document.getElementById('labelValue')
        const arrow = document.getElementById('arrow')

        if(value !== 0)
          value--
        else
          value = 0

        labelValue.innerHTML = value
        arrow.style.transform = 'rotate('+value*1.18+'deg)'
      },

    }
  }

</script>
