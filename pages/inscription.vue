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
        <GenderSelect v-model="inputGender" />
      </template>

      <template #step4>
        <h3 style="font-weight: bold;">Récapitulatif</h3>
        <p>Je m'appelle : <span>{{ inputName }}</span></p>
        <p>Je suis de : <span>{{ inputLocation }}</span></p>
        <p>Je recherche : <span>{{
          inputGender === "women" ? "une femme" : (
            inputGender === "men" ? "un homme" : "peu importe"
          )
        }}</span></p>
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
const inputGender = ref('')

const onSubmit = () => {
  console.log('Form submitted')
  console.log('Name:', inputName.value)
  console.log('Location:', inputLocation.value)
  console.log('Gender:', inputGender.value)
}
</script>

<style scoped>
h3 {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

p > span {
  font-weight: bold;
}
</style>
