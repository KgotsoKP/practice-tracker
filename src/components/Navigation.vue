<template>
  <header class="bg-at-light-green text-white">
    <nav class="container py-5 px-4 flex-col gap-4 items-counter sm:flex-row">
      <div class="felx items-center gap-x-4">
        <h1 text-white>YASS PT</h1>
      </div>

      <ul class="flex flex-1 justify-end gap-x-10">
        <router-link class="cursor-pointer text-white" :to="{ name: 'home' }">Home</router-link>
        <router-link v-if="user" class="cursor-pointer text-white" :to="{ name: 'register' }">Create</router-link>
        <router-link v-if="!user" class="cursor-pointer text-white" :to="{ name: 'login' }">Login</router-link>
        <li v-if="user" @click="logout" class="cursor-pointer">Logout</li>
      </ul>
    </nav>
  </header>
</template>
  
<script>
import { supabase } from '@/superbase/init';
import { useRouter } from 'vue-router';
import { computed } from 'vue';
import store from '@/store/index';

export default {
  setup() {
    // Get user from store
    const user = computed(() => store.state.user)
    // Setup ref to router
    const router = useRouter();
    
    // Logout function
    const logout = async () => {
      await supabase.auth.signOut();
      router.push({name: 'home'});
    }
    return { logout, user };
  },
};
</script>