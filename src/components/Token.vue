<script setup>
import { computed } from 'vue';
import { formatBytes32String } from '@ethersproject/strings';
import { getUrl } from '@snapshot-labs/snapshot.js/src/utils.ts';

const props = defineProps({
  space: Object,
  size: String,
  symbolIndex: [String, Number]
});

const spaceId = computed(() => props.space.id);

const url = computed(() => {
  const url = getUrl(props.space.avatar);
  if (!url) return '';
  return `https://worker.snapshot.org/mirror?img=${encodeURIComponent(url)}`;
});

const spaceAddress = computed(() => {
  if (spaceId.value) return formatBytes32String(spaceId.value.slice(0, 24));
  return '';
});
</script>

<template>
  <span class="inline-block align-middle leading-none">
    <UiAvatar
      :space="space"
      :imgsrc="url"
      :address="spaceAddress"
      :size="size"
    />
  </span>
</template>
