<script setup>
import { useOnline } from '@vueuse/core'

const online = useOnline()

onMounted(() => {
  // Approach 1: Using the offline event
  // window.addEventListener("offline", (e) => {
  //   //displays an error when the user is not connected to the internet
  //   showError({ message: '⚠️ You are not connected to the internet!', statusCode: 503 });
  // });
});

// Approach 2: Using useOnline from the vueuse pacakge
watch(online,(newValue, oldValue) => {
  if (!newValue) {
    showError({ message: '⚠️ You are not connected to the internet!', statusCode: 503 });
  }
});
</script>

<template>
  <NuxtLayout name="default">
    <h1 class="main-app__title">Your app is {{ online ? 'Online' : 'Offline' }}</h1>
    <p class="main-app__text">Some sample text... <br/> 
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus, iste nam velit exercitationem in maiores recusandae harum repudiandae sint dolores, culpa libero necessitatibus voluptate consectetur minima beatae amet consequatur ipsam.
    </p>
  </NuxtLayout>
</template>


