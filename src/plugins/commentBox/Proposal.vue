<script setup>
defineProps({
  proposal: Object,
  space: Object,
  loadedResults: Boolean
});
</script>

<template>
  <PluginCommentBoxCustomBlock
    :proposalId="proposal.id"
    :proposal="proposal"
    :space="space"
  />
</template>
