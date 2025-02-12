<template>
  <MultiStepLoader
    :steps="loadingSteps"
    :loading="props.isLoading"
    :prevent-close="true"
    @complete="handleLoadingComplete"
  />
</template>

<script setup lang="ts">
import Button from "@/components/ui/button/Button.vue";
import MultiStepLoader from "@/components/ui/MultiStepLoader.vue";

const props = defineProps<{
  isLoading: boolean;
}>();

const emit = defineEmits<{
  complete: () => void;
}>();

interface Step {
  text: string; // Display text for the step
  afterText?: string; // Text to show after step completion
  async?: boolean; // If true, waits for external trigger to proceed
  duration?: number; // Duration in ms before proceeding (default: 2000)
  action?: () => void; // Function to execute when step is active
}
// State management
const loaderStates = reactive({
  isProcessing: false,
  isSavingOrder: false,
  sendingMails: false,
});

const uiState = reactive({
  isAfterTextLoading: false,
  closeSimple: () => {
    props.isLoading = false;
  },
  closeAsync: () => {
    uiState.isAfterTextLoading = false;
  },
});

// Simple loading steps configuration
const loadingSteps = computed<Step[]>(() => [
  {
    text: "Vérification des données",
    duration: 1500,
  },
  {
    text: "Recherche de profils compatibles",
    duration: 2000,
  },
  {
    text: "Analyse des résultats par l'intelligence artificielle",
    duration: 1500,
  },
  {
    text: "Calcul des probabilités de match",
    duration: 1800,
  },
  {
    text: "Redirection",
    duration: 1000,
    action: handleLoadingComplete,
  },
]);

function handleLoadingComplete() {
  // Emit event to parent component
  emit("complete");
}
</script>
