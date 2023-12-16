<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="max-w-screen-sm mx-auto px-4 py-10">
        <!-- Error Handling -->
        <div v-if="errorMsg" class="mb-10 p-4 rounded-md bg-light-grey">
            <p class="text-red-500">{{ errorMsg }}</p>
        </div>
    </div>

    <!-- Register Form -->
    <form class="max-w-screen-sm mx-auto p-8 flex flex-col bg-light-grey rounded-md shadow-lg">
        <h1 class="text-3xl text-at-light-green mb-4">Register</h1>

        <div class="flex flex-col mb-2">
            <label for="email" class="mb-1 text-sm text-at-light-green">Email</label>
            <input type="email" placeholder="name@email.com" name="email" required
                class="p-2 text-gray-500 focus:outline-none" v-model="email" id="password">
        </div>

        <div class="flex flex-col mb-2">
            <label for="password" class="mb-1 text-sm text-at-light-green">Password</label>
            <input type="password" name="password" required class="p-2 text-gray-500 focus:outline-none" v-model="password"
                id="password">
        </div>

        <div class="flex flex-col mb-2">
            <label for="confirmPassword" class="mb-1 text-sm text-at-light-green">Confirm Password</label>
            <input type="password" name="confirmPassword" required class="p-2 text-gray-500 focus:outline-none"
                v-model="confirmPassword" id="confirmPassword">
        </div>

        <button type="submit" class="mt-6 py-2 px-6 rounded-sm slef-start text-sm text-white bg-at-light-green duration-200 border-solid
        border-2 border-transparent hover:border-white hover:bg-white
        hover:text-at-light-green">Register</button>
    </form>
</template>
  
<script>
import { ref } from 'vue';

export default {
    name: "register",
    setup() {
        // Create data / vars
        const email = ref(null);
        const password = ref(null);
        const confirmPassword = ref(null);
        const errorMsg = ref(null);

        // Register function
        return { email, password, confirmPassword, errorMsg };
    },
};
</script>