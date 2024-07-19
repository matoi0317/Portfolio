<template>
  <div>
    <GlobalHeader />
    <div class="work-container">
      <WorkList />
    </div>
  </div>
</template>

<script setup lang="ts">
import GlobalHeader from '~/components/GlobalHeader.vue';
import WorkList from '~/components/pages/works/WorkList.vue'
</script>

<style scoped lang="scss">
.work-container {
  width: 100%;
  height: 100%;
  background-color: #131415;
}
</style>