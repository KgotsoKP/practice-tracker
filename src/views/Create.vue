<template>
    <div class="ma-w-screen-md mx-auto px-4 py-10">
      <!-- Status Message -->
      <div v-if="statusMsg || errorMsg" class="mb-10 p-4 bg-light-grey rounded-md">
       <p class="text-at-light-green"> {{  statusMsg }}</p>
       <p class="text-red-500"> {{  errorMsg }}</p>
      </div>

      <!-- Create Form -->
      <div class="p-8 flex items-start bg-light-grey rounded-md shadow-lg">
        <!-- Form -->
        <form action="" class="flex flex-col gap-y-5 w-full">

          <h1 class="text-2xl text-at-light-green">Record Practice Session</h1>

          <!-- Practice Session Subject -->
          <div class="flex flex-col">
            <label for="practice-subject" class="mb-1 text-sm text-at-light-green">subject</label>
          </div>
        </form>
      </div>
      <h1>Create Practice Session Page / View</h1>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  export default {
    name: "create",
    setup() {
      // Create data
      const practiceSubject = ref("");
      const practiceAssessment = ref("select-assessment");
      const practiceMaterial = ref([]);
      const practiceDate = ref("");

      const statusMsg = ref(null);
      const errorMsg = ref(null);
  
      // Add exercise
  
      // Delete exercise
  
      // Listens for chaging of practice session type input
  
      // Create workout
  
      return { practiceAssessment, practiceSubject, practiceMaterial, practiceDate, statusMsg, errorMsg };
    },
  };
  </script>