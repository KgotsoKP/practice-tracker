<template>
  <div class="min-h-full" v-if="appReady">
    <Navigation></Navigation>
    <router-view />
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue';
import { ref } from 'vue';
import { supabase } from './superbase/init';
import store from './store/index';

export default {
  components: {
    Navigation,
  },
  setup() {
    // Create data / vars
    const appReady = ref(null)

    // Check to see if user is already logged in
    const user = supabase.auth.getUser();

    // If user does not exist, need to make app ready
    if (!user) {
      appReady.value = true
    }
    // Runs when there is a auth state change
    // if user is logged in, this will fire
    supabase.auth.onAuthStateChange((_, session) => {
      console.log("hello")
      store.methods.setUser(session);
      appReady.value = true;
    })

    return {appReady};
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap");
</style>