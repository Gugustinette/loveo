<template>
  <AuroraBackground>
    <Form :total-steps="4" @submit="onSubmit">
      <template #step1>
        <Label for="input-name">Nom</Label>
        <IInput
          id="input-name"
          name="input-name"
          placeholder="Je m'appelle..."
          container-class="w-full max-w-sm"
          v-model:modelValue="inputName"
        ></IInput>
      </template>

      <template #step2>
        <Label for="input-name">Lieu</Label>
        <IInput
          id="input-name"
          name="input-name"
          placeholder="Je suis de..."
          container-class="w-full max-w-sm"
          v-model:modelValue="inputLocation"
        ></IInput>
      </template>

      <template #step3>
        <Label for="input-name">Préférence</Label>
        <GenderSelect />
      </template>

      <template #step4>
        <h3>Récapitulatif</h3>
      </template>
    </Form>
  </AuroraBackground>
</template>

<script setup lang="ts">
import AuroraBackground from "@/components/ui/AuroraBackground.vue";
import Form from '@/components/Form.vue'
import IInput from '@/components/ui/IInput.vue'
import Label from '@/components/ui/label/Label.vue'
import { ref } from 'vue'

const inputName = ref('')
const inputLocation = ref('')

const onSubmit = () => {
  console.log('Form submitted')
  console.log('Name:', inputName.value)
  console.log('Location:', inputLocation.value)
}
</script>

<style scoped>
</style>
