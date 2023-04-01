<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Loader from './components/Loader.vue';
import WelcomeTitle from './components/WelcomeTitle.vue';
import WelcomeText from './components/WelcomeText.vue';
import CreateMonster from './components/CreateMonster.vue';


const isLoading = ref(true);
onMounted(() => {
  setTimeout(() => {
    isLoading.value = false;
  }, 4500)
})

const show = ref(false);
const showMonsterCreater = () => {
    show.value = true;
}
</script>

<template>
  <Loader v-if="isLoading"></Loader>
  <div v-else class="content">
    <div v-if="!show">
      <WelcomeTitle></WelcomeTitle>
      <WelcomeText></WelcomeText>
      <button type="button" @click="showMonsterCreater">Start</button>
    </div>
    <div v-else>
      <CreateMonster></CreateMonster>
    </div>
  </div>
</template>

<style scoped>
    .content {
        animation: show 3s;
    }

    @keyframes show {
        0% {
            opacity: 0;
        }
        8% {
          opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }
</style>
