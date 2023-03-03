<template>
        <router-view v-slot="{ Component }">
            <transition name="slide-fade" v-if="pageLoaded">
                <component :is="Component"></component>
            </transition>
        </router-view>
</template>

<script>
import {ref, onMounted, nextTick} from 'vue'
export default {
    setup() {
        let pageLoaded = ref(false);
        
        onMounted(async () => {
            await nextTick()
            pageLoaded.value = true
        });

        return {
            pageLoaded
        }
    },
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
body, html {
     padding: 0;
     margin: 0;
     width: 100%;
     min-height: 100vh;
}

body {
    --tw-bg-opacity: 1;
    background-color: rgb(243 244 246 / var(--tw-bg-opacity));
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}
</style>
