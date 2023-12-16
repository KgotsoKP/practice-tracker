<template>
    <header class="bg-at-light-green text-white">
        <nav class="container py-5 px-4 flex-col gap-4 items-counter sm:flex-row">
            <div class="felx items-center gap-x-4">
                <h1 text-white>YASS PT</h1>
            </div>

            <ul class="flex flex-1 justify-end gap-x-10">
                <router-link class="cursor-pointer text-white" :to="{name : 'home'}">Home</router-link>
                <router-link class="cursor-pointer text-white" :to="{name : ''}">Create</router-link>
                <router-link class="cursor-pointer text-white" :to="{name : ''}">Login</router-link>
                <li class="cursor-pointer">Logout</li>
            </ul>
        </nav>
    </header>
    <h1>Hello form navigation</h1>
  </template>
  
  <script>
  export default {
    setup() {
      // Get user from store
  
      // Setup ref to router
  
      // Logout function
  
      return {};
    },
  };
  </script>