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

        <ion-input placeholder="Username" style="color: white; border-bottom: 1px solid gray;"></ion-input>
        <ion-input placeholder="Password" style="color: white; border-bottom: 1px solid gray;"></ion-input>
        <ion-button>LOGIN</ion-button>

      </div>


    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonInput, IonButton } from '@ionic/vue';
</script>
