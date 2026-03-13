<script setup lang="ts">
import { sectionId, SectionType } from '@/constants/sections'
</script>

<template>
  <VSheet :id="sectionId(SectionType.Introduction)" class="pa-4 mt-2" rounded border>
    <div class="mb-4">
      <div class="text-h5 font-weight-bold mb-2">Introduction</div>
    </div>
    <div class="text-justify mb-2">
      Hello! I’m <span class="font-weight-bold">Aimee (Thi Cam Tien) Le</span>
    </div>

  </VSheet>
</template>
