<template>
  <AuthLayout :title="title" :description="description">
    <slot/>
  </AuthLayout>
</template>

<script setup lang="ts">
// import AuthLayout from '@/Layouts/Auth/AuthSimpleLayout.vue';
// import AuthLayout from '@/Layouts/Auth/AuthSplitLayout.vue';
import AuthLayout from '@/Layouts/Auth/AuthCardLayout.vue';

defineProps<{
  title?: string;
  description?: string;
}>();
</script>
