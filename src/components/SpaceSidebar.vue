<script setup>
defineProps({
  space: Object
});
</script>

<template>
  <div style="position: fixed; width: 240px">
    <Block :slim="true" class="overflow-hidden">
      <SpaceSidebarHeader :space="space" />
      <SpaceSidebarNavigation :space="space" />
    </Block>
  </div>
</template>
