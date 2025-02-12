<template>
  <AuroraBackground>
    <Motion
      as="div"
      :initial="{ opacity: 0, y: 40, filter: 'blur(10px)' }"
      :in-view="{
        opacity: 1,
        y: 0,
        filter: 'blur(0px)',
      }"
      :transition="{
        delay: 0.3,
        duration: 0.8,
        ease: 'easeInOut',
      }"
      class="relative flex flex-col items-center justify-center gap-4 px-4"
    >
      <div class="text-center text-3xl font-bold md:text-7xl dark:text-white">
        Loveo.
      </div>
      <div class="py-4 text-base font-extralight md:text-4xl dark:text-neutral-200">
        L'app de rencontre boostée à l'IA.
      </div>
      <div class="flex min-h-64 items-center justify-center">
        <InteractiveHoverButton class="w-48" text="Je m'inscris" />
      </div>
    </Motion>
  </AuroraBackground>
</template>

<script setup lang="ts">
import { Motion } from "motion-v";
import AuroraBackground from "@/components/ui/AuroraBackground.vue";
import InteractiveHoverButton from "@/components/ui/InteractiveHoverButton.vue";

useSeoMeta({
  title: 'Loveo',
  ogTitle: 'Loveo',
  description: "Le site de rencontre boostée à l'IA.",
  ogDescription: "Le site de rencontre boostée à l'IA.",
  // ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})
</script>
