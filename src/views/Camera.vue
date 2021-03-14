<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Camera</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Camera</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-button type="submit" @click="takePicture()">Take a photo</ion-button>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { CameraResultType, CameraSource, Plugins } from '@capacitor/core';

const { Camera } = Plugins;

export default  {
  name: 'Camera',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage },

  methods: {
    async takePicture() {
      const image = await Camera.getPhoto({
        quality: 100,
        allowEditing: true,
        saveToGallery: true,
        source: CameraSource.Camera,
        resultType: CameraResultType.Uri
      });
      // image.webPath will contain a path that can be set as an image src.
      // You can access the original file using image.path, which can be
      // passed to the Filesystem API to read the raw data of the image,
      // if desired (or pass resultType: CameraResultType.Base64 to getPhoto)
      const imageUrl = image.webPath;
      // Can be set to the src of an image now
      console.log(imageUrl);
    }
  }
}
</script>
