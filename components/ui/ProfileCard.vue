<template>
  <ClientOnly>
    <CardContainer>
      <CardBody
        class="group/card relative size-auto rounded-xl border border-black/[0.1] bg-gray-50 p-6 sm:w-[30rem] dark:border-white/[0.2] dark:bg-black dark:hover:shadow-2xl dark:hover:shadow-emerald-500/[0.1]"
      >
        <CardItem
          :translate-z="50"
          class="text-2xl font-bold text-neutral-600 dark:text-white"
        >
          Augustin
        </CardItem>
        <CardItem
          :translate-z="100"
          class="mt-4 w-full"
        >
          <NuxtImg
            src="/img-profile-card.jpg"
            height="1000"
            width="1000"
            class="h-200 w-full rounded-xl object-cover group-hover/card:shadow-xl"
            alt="thumbnail"
          />
        </CardItem>
        <CardItem
          class="mt-2 flex items-center gap-2 text-sm text-neutral-500 dark:text-neutral-300"
          :translate-z="60"
        >
          <div class="flex items-center gap-1">
            <Icon name="mdi:location" size="16" />
            <span>Nantes</span>
          </div>
        
          <div class="flex items-center gap-1">
            <Icon name="mdi:cake" size="16" />
            <span>22 ans</span>
          </div>
        </CardItem>
        <CardItem
          as="p"
          translate-z="60"
          class="mt-4 text-sm text-neutral-500 dark:text-neutral-300"
        >
          Oui y a que moi qui ai un profil ici, et alors ? <br />
        </CardItem>

        <CardItem
          :translate-z="70"
          class="mt-4 flex flex-wrap gap-2"
        >
          <span
            class="rounded-full bg-emerald-100 px-3 py-1 text-xs font-semibold text-emerald-700 dark:bg-emerald-700 dark:text-emerald-100"
          >
            Jeux Vidéo
          </span>
          <span
            class="rounded-full bg-emerald-100 px-3 py-1 text-xs font-semibold text-emerald-700 dark:bg-emerald-700 dark:text-emerald-100"
          >
            Internet
          </span>
          <span
            class="rounded-full bg-emerald-100 px-3 py-1 text-xs font-semibold text-emerald-700 dark:bg-emerald-700 dark:text-emerald-100"
          >
            Sport
          </span>
          <span
            class="rounded-full bg-emerald-100 px-3 py-1 text-xs font-semibold text-emerald-700 dark:bg-emerald-700 dark:text-emerald-100"
          >
            Piano
          </span>
          <span
            class="rounded-full bg-emerald-100 px-3 py-1 text-xs font-semibold text-emerald-700 dark:bg-emerald-700 dark:text-emerald-100"
          >
            Musique
          </span>
        </CardItem>

        <div
          class="bottom-4 left-4 flex items-center gap-3 mt-4"
        >
          <a
            href="https://instagram.com/gugustinette"
            class="text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-200"
          >
            <Icon name="mdi:instagram" size="20" />
          </a>
          <a
            href="https://twitter.com/gugustinette"
            class="text-gray-500 hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-200"
          >
            <Icon name="mdi:twitter" size="20" />
          </a>
        </div>
      </CardBody>
    </CardContainer>
  </ClientOnly>
</template>

<script setup lang="ts">
import CardContainer from "@/components/ui/card-3d/CardContainer";
import CardBody from "@/components/ui/card-3d/CardBody";
import CardItem from "@/components/ui/card-3d/CardItem";
</script>
