<template>
  <nav>
    <NuxtLink to="/">Loveo.</NuxtLink>
  </nav>
  <AuroraBackground>
    <main>
      <p>Voici votre âme-soeur !</p>
      <ProfileCard />
      <ShareOnTwitter :text="`J'ai trouvé mon âme-soeur sur Loveo !\n@gugustinette est vraiment magnifique purée la dinguerie\n\n`" url="https://loveo.com" />
    </main>
  </AuroraBackground>
</template>

<script setup lang="ts">
import AuroraBackground from "@/components/ui/AuroraBackground.vue";
import ProfileCard from "@/components/ui/ProfileCard.vue";
import ShareOnTwitter from "@/components/ShareOnTwitter.vue";
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
