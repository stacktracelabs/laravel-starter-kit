<template>
  <AppShell class="flex-col">
    <AppHeader :breadcrumbs="breadcrumbs"/>
    <AppContent>
      <slot/>
    </AppContent>
  </AppShell>
</template>

<script setup lang="ts">
import AppContent from '@/Components/AppContent.vue';
import AppHeader from '@/Components/AppHeader.vue';
import AppShell from '@/Components/AppShell.vue';
import type { BreadcrumbItemType } from '@/Types';

interface Props {
  breadcrumbs?: BreadcrumbItemType[];
}

withDefaults(defineProps<Props>(), {
  breadcrumbs: () => [],
});
</script>
