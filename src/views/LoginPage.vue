<template>
  <ion-page>
    <ion-header :translucent="true" class="text-center">
      <ion-toolbar color="primary">
        <ion-title>
          <a href="/" class="title">Aplikasi Negova</a>
        </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <div class="bg">
        <ion-grid class="ion-padding">
          <ion-row style="height:50%">
            <ion-col class="text-center">
              <h1 class="salam">
                Selamat Datang <br>
                Negova Julyan Herman <br>
              </h1>
              <img src="/assets/img/wong.png" alt="" class="wong">
            </ion-col>
          </ion-row>
          <ion-row style="height:50%;">
            <ion-col>
              <div class="menu">Login</div>
              <ion-card style="margin-right: 3px;margin-left: 3px;">
                <ion-card-content>
                  <ion-grid style="margin-left:-5%;margin-right:-5%;margin-bottom:-10%;">
                    <ion-row>
                      <ion-col>
                        <ion-item
                          style="display:inline-block;z-index: 1;position:relative;width:100%;margin-top:-20px;">
                          <ion-label position="floating"
                            style="margin-bottom:-10px;">Username</ion-label>
                          <ion-input v-model="username"></ion-input>
                        </ion-item>
                      </ion-col>
                      <ion-col size="3" class="text-center" style="z-index:2;position:absolute;right:-10px;top:18px;">
                        <ion-icon :icon="personOutline" class="icone"></ion-icon>
                      </ion-col>
                    </ion-row>
                    <ion-row>
                      <ion-col>
                        <ion-item
                          style="display:inline-block;z-index: 1;position:relative;width:100%;margin-top:-16px;">
                          <ion-label position="floating"
                            style="margin-bottom:-10px;">Password</ion-label>
                          <ion-input type="password" v-model="password"></ion-input>
                        </ion-item>
                      </ion-col>
                      <ion-col size="3" class="text-center" style="z-index:2;position:absolute;right:-10px;bottom:2px;">
                        <ion-icon :icon="lockClosedOutline" class="icone"></ion-icon>
                      </ion-col>
                    </ion-row>
                  </ion-grid>
                </ion-card-content>
              </ion-card>
              <ion-button expand="block" class="btn-login" size="large" @click="cekLogin">
                Login
              </ion-button>
            </ion-col>
          </ion-row>
        </ion-grid>
      </div>
    </ion-content>
  </ion-page>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton, IonCard, IonCardContent, IonInput, IonLabel, IonItem, IonIcon, alertController } from '@ionic/vue';
import { personOutline, lockClosedOutline } from 'ionicons/icons';

export default defineComponent({
  name: 'LoginPage',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonButton,
    IonCard,
    IonCardContent,
    IonItem,
    IonInput,
    IonLabel,
    IonIcon
  },
  methods: {
    cekLogin() {
      if (this.username == "negova" && this.password == "negova") {
        this.Pesan('Berhasil Login');
      } else {
        this.Pesan('Gagal Login');
      }
    }
  },
  data() {
    const Pesan = async (text: string) => {
      const alert = await alertController.create({
        header: 'Alert',
        message: text,
        buttons: ['OK'],
      });

      await alert.present();
    };

    return {
      username: '',
      password: '',

      personOutline,
      lockClosedOutline,
      Pesan
    }
  }
});
</script>
  
<style scoped>
.text-center {
  text-align: center;
}

.title {
  color: white;
  text-decoration: none;
}

.wong {
  width: 60%;
  margin-top: 5%;
  margin-bottom: -5%;
}

.bg {
  background-color: #3880ff;
  height: 50%;
  border-bottom-right-radius: 15%;
  border-bottom-left-radius: 15%;
}

.salam {
  margin-top: 15%;
  color: white;
}

.menu {
  color: #083d97;
  font-weight: bold;
  font-size: 22px;
}

.icone {
  font-size: 25px;
  color: #3880ff;
}

ion-button {
  text-transform: none;
}

.btn-login {
  margin-top: 15px;
  height: 25%;
}
</style>
  