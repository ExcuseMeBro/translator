<script setup>
import { computed, onMounted } from "vue";
import { useRouter } from "vue-router";

const defaultLayout = "login";

const { currentRoute } = useRouter();

const layout = computed(
  () => `${currentRoute.value.meta.layout || defaultLayout}-layout`
);

</script>

<template>
  <div>
    <component :is="layout">
      <router-view />
    </component>
  </div>
</template>

<style scoped>
</style>
