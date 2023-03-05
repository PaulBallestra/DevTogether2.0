<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">

        <ion-tab-button tab="loginPage" href="/tabs/login">
          <ion-img style="width: 25px; margin-bottom: 5px;;" src="assets/icon/login.svg"></ion-img>
          <ion-label>Login</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="dashboard" href="/tabs/dashboard">
          <ion-img style="width: 25px; margin-bottom: 5px;" src="assets/icon/dashboard.svg"></ion-img>
          <ion-label>Dashboard</ion-label>
        </ion-tab-button>

      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonPage, IonRouterOutlet, IonImg } from '@ionic/vue';
import {  } from 'ionicons/icons';
</script>
