<template>
  <div class="form-container">
    <AnimatePresence mode="out-in" :initial="false">
      <Motion
        :key="currentStep"
        class="step-container"
        :initial="{
          position: 'absolute',
          opacity: 0,
          x: -50,
          left: '50%',
          translateX: '-50%',
        }"
        :animate="{
          position: 'absolute',
          opacity: 1,
          x: 0,
          left: '50%',
          translateX: '-50%',
        }"
        :exit="{
          position: 'absolute',
          opacity: 0,
          x: 50,
          left: '50%',
          translateX: '-50%',
        }"
        :transition="{ duration: 0.3, ease: 'easeInOut' }"
      >
        <div class="slot-container" @keydown.enter="handleEnter">
          <slot :name="currentSlotName" :focus-input="focusInput" />
        </div>

        <div class="button-container">
          <Button variant="outline" v-if="currentStep > 1" @click="prevStep">
            Précédent
          </Button>
          <Button @click="nextStep">
            {{ currentStep === props.totalSteps ? 'Rechercher' : 'Suivant' }}
          </Button>
        </div>
      </Motion>
    </AnimatePresence>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import { AnimatePresence, Motion } from 'motion-v'
import Button from '@/components/ui/button/Button.vue'

const props = defineProps({
  totalSteps: {
    type: Number,
    required: true,
  },
})

const emit = defineEmits(['submit'])

const currentStep = ref(1)
let inputRef = null

const nextStep = () => {
  if (currentStep.value < props.totalSteps) {
    currentStep.value++
  } else {
    // Handle form submission
    emit('submit')
  }
}

const prevStep = () => {
  if (currentStep.value > 1) {
    currentStep.value--
  }
}

const currentSlotName = computed(() => `step${currentStep.value}`)

const handleEnter = () => {
  nextStep()
}

const focusInput = (el: any) => {
  inputRef = el
  onMounted(() => {
    if (inputRef) {
      inputRef.focus()
    }
  })
}
</script>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  position: relative;
  height: 200px;
}

.step-container {
  display: flex;
  flex-direction: column;
  row-gap: 50px;
  width: 100%;
  max-width: 400px;
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 20px;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
}

.slot-container {
  display: flex;
  flex-direction: column;
  row-gap: 10px;
}

.button-container {
  display: flex;
  justify-content: space-between;

  &:has(> :last-child:nth-child(1)) {
    justify-content: flex-end;
  }
}
</style>
