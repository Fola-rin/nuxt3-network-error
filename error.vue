<script setup>
import { useOnline } from '@vueuse/core'

const online = useOnline()

defineProps({
  error: Object
})
onMounted(() => {
    //Approach 1
    // window.addEventListener("online", (e) => {
    //     //clear the error once the application detects an online connection
    //     clearError({ redirect: '/' });
    // });

    //Approach 2
    watch(online,(newValue, oldValue) => {
        if (newValue) {
            clearError({ redirect: '/' });
        }
    });
});
</script>

<template>
    <NuxtLayout name="default">
        <h1 class="main-app__title">{{ error.statusCode }}</h1>
        <p class="main-app__text">{{ error.message }}</p>
    </NuxtLayout>
</template>