<template>
  <header class="flex h-16 shrink-0 items-center gap-2 border-b border-sidebar-border/70 px-6 transition-[width,height] ease-linear group-has-data-[collapsible=icon]/sidebar-wrapper:h-12 md:px-4">
    <div class="flex items-center gap-2">
      <SidebarTrigger class="-ml-1"/>
      <template v-if="breadcrumbs && breadcrumbs.length > 0">
        <Breadcrumbs :breadcrumbs="breadcrumbs"/>
      </template>
    </div>
  </header>
</template>

<script setup lang="ts">
import Breadcrumbs from '@/Components/Breadcrumbs.vue';
import { SidebarTrigger } from '@/Components/Sidebar';
import type { BreadcrumbItemType } from '@/Types';

withDefaults(
  defineProps<{
    breadcrumbs?: BreadcrumbItemType[];
  }>(),
  {
    breadcrumbs: () => [],
  },
);
</script>
