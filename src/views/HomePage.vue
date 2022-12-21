<template>
  <ion-page>
    <ion-header :translucent="true" class="text-center">
      <ion-toolbar color="primary">
        <ion-title>Aplikasi Negova</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <div id="container">
        <strong>Sudah Punya Akun?</strong>
        <p>Silahkan Login dibawah ini</p>
        <p>
          <br>
          <ion-button href="/login">
            Login
          </ion-button>
        </p>
        <br>
        <strong>Belum Punya Akun?</strong>
        <p>Silahkan Daftar dibawah ini</p>
        <p>
          <br>
          <ion-button href="/">
            Daftar
          </ion-button>
        </p>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomePage',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonButton
  }
});
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}

.text-center {
  text-align: center;
}

ion-button {
  text-transform: none;
}
</style>
