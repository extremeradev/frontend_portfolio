<template>
    <div>
      <!-- Contenido principal -->
      <slot></slot>
  
      <!-- Overlay de loading -->
      <div
        v-if="loadingStore.isLoading"
        class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50"
      >
        <div class="animate-spin w-12 h-12 border-4 border-blue-500 border-t-transparent rounded-full"></div>
      </div>
    </div>
  </template>
  
  <script>
  import { useLoadingStore } from "@/stores/loading";
  
  export default {
    setup() {
      const loadingStore = useLoadingStore();
  
      return {
        loadingStore,
      };
    },
  };
  </script>