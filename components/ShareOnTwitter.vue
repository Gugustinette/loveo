<template>
  <Button @click="shareOnTwitter">
    <Icon name="mdi:share" size="24" />
    Partager
  </Button>
</template>

<script setup lang="ts">
import Button from './ui/button/Button.vue';
import { defineProps } from 'vue';

interface Props {
  text: string;
  url: string;
}

const props = defineProps<Props>();

const shareOnTwitter = () => {
  const encodedText = encodeURIComponent(props.text);
  const encodedUrl = encodeURIComponent(props.url);
  const twitterURL = `https://twitter.com/intent/tweet?text=${encodedText}&url=${encodedUrl}`;

  window.open(twitterURL, '_blank', 'noopener,noreferrer');
};
</script>
