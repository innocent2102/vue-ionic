<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Home</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Home</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Home page" />
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

@Options({
  components: { ExploreContainer, IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
})
export default class Home extends Vue {}

</script>
