<script setup lang="ts">
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select'
import type { SelectRootEmits, SelectRootProps } from 'radix-vue'
import { SelectRoot, useForwardPropsEmits } from 'radix-vue'

const props = defineProps<SelectRootProps>()
const emits = defineEmits<SelectRootEmits>()

const forwarded = useForwardPropsEmits(props, emits)
</script>

<template>
  <Select v-bind="forwarded">
    <SelectTrigger>
      <SelectValue placeholder="Je recherche ..." />
    </SelectTrigger>
    <SelectContent>
      <SelectGroup>
        <SelectItem value="men">
          Un homme
        </SelectItem>
        <SelectItem value="women">
          Une femme
        </SelectItem>
        <SelectItem value="anything">
          Peu importe
        </SelectItem>
      </SelectGroup>
    </SelectContent>
  </Select>
</template>
