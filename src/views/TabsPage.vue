<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">

        <ion-tab-button tab="loginPage" href="/tabs/loginPage">
          <ion-icon name="log-in-outline"></ion-icon>
          <ion-label>Login</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="dashboard" href="/tabs/dashboard">
          <ion-label>Dashboard</ion-label>
        </ion-tab-button>

      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup lang="ts">
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage, IonRouterOutlet } from '@ionic/vue';
import {  } from 'ionicons/icons';
</script>
