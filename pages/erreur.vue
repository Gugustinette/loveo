<template>
  <nav>
    <NuxtLink to="/">Loveo.</NuxtLink>
  </nav>
  <AuroraBackground>
    <main>
      <p>Il semble qu'aucun profil ne corresponde à vos critères de recherche. 😕</p>
      <ShareOnTwitter :text="`Super nul cette appli !\nMais @gugustinette est quand même bien sympa vous trouvez pas ? ^^\n\n`" url="https://loveo.com" />
    </main>
  </AuroraBackground>
</template>

<script setup lang="ts">
import AuroraBackground from "@/components/ui/AuroraBackground.vue";
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
