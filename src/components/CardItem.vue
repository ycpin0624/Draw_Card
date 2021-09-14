<template>
  <div id="CardItem">
    <!-- Card 1 -->
    <transition>
      <img
        id="card1"
        v-bind:src="require('@/components/CardPic/' + ImgUrl1)"
        v-on:click="isShow1 = !isShow1"
        v-show="isShow1"
      />
    </transition>
    <img
      id="target1"
      v-bind:src="require('@/components/TargetPic/' + TargetImg1)"
      v-show="!isShow1"
    />

    <!-- Card 2 -->
    <transition>
      <img
        id="card2"
        v-bind:src="require('@/components/CardPic/' + ImgUrl2)"
        v-on:click="isShow2 = !isShow2"
        v-show="isShow2"
      />
    </transition>
    <img
      id="target2"
      v-bind:src="require('@/components/TargetPic/' + TargetImg2)"
      v-show="!isShow2"
    />

    <!-- Card 3 -->
    <transition>
      <img
        id="card3"
        v-bind:src="require('@/components/CardPic/' + ImgUrl3)"
        v-on:click="isShow3 = !isShow3"
        v-show="isShow3"
      />
    </transition>
    <img
      id="target3"
      v-bind:src="require('@/components/TargetPic/' + TargetImg3)"
      v-show="!isShow3"
    />
  </div>
</template>

<script>
import { initializeApp } from "firebase/app";
import { getStorage } from "firebase/storage";

// Set the configuration for your app
// TODO: Replace with your app's config object
const firebaseConfig = {
  apiKey: '<your-api-key>',
  authDomain: '<your-auth-domain>',
  databaseURL: '<your-database-url>',
  storageBucket: '<your-storage-bucket-url>'
};
const firebaseApp = initializeApp(firebaseConfig);

// Get a reference to the storage service, which is used to create references in your storage bucket
const storage = getStorage(firebaseApp);


export default {
  data() {
    return {
      ImgUrl1: "Card1.jpg",
      ImgUrl2: "Card2.jpg",
      ImgUrl3: "Card3.jpg",
      TargetImg1: "1.jpg",
      TargetImg2: "2.jpg",
      TargetImg3: "3.jpg",
      isShow1: true,
      isShow2: true,
      isShow3: true,
    };
  },
};
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 1s;
}
.v-enter-from,
.v-leave-to {
  opacity: 0;
}
.v-enter-to,
.v-leave-from {
  opacity: 1;
}
</style>

<style>
#card1,
#target1 {
  left: 350px;
}

#card2,
#target2 {
  left: 750px;
}

#card3,
#target3 {
  left: 1150px;
}

#card1,
#card2,
#card3 {
  z-index: 1;
}
</style>

<style>
#CardItem img {
  position: absolute;
  width: 350px;
  border-radius: 5px;
  top: 150px;
  cursor: pointer;
}

#CardItem img:hover {
  animation: scaleDrawIN 0.3s ease;
  transform: scale(1.05);
}

#CardItem img:not(:hover) {
  animation: scaleDrawOUT 0.3s ease;
}

@keyframes scaleDrawIN {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.05);
  }
}

@keyframes scaleDrawOUT {
  0% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}
</style>