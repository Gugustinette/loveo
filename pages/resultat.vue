<template>
  <AuroraBackground>
    <main>
      <p>Voici votre âme-soeur !</p>
      <ProfileCard />
    </main>
  </AuroraBackground>
</template>

<script setup lang="ts">
import AuroraBackground from "@/components/ui/AuroraBackground.vue";
import ProfileCard from "@/components/ui/ProfileCard.vue";
</script>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  row-gap: 2rem;
  height: 100vh;
}
</style>
