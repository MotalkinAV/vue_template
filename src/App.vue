<template>
  <component v-if="layout" :is="layoutToRender"/>
</template>

<script setup>
import { useRoute } from "vue-router";
import { computed, defineAsyncComponent } from "vue";

const route = useRoute();

const layout = computed(() => route.meta.layout);

function loadLayout(name) {
  return defineAsyncComponent(() => import(`./layouts/${name}Layout.vue`));
}

const layoutToRender = computed(() => {
  return loadLayout(layout.value);
});
</script>
