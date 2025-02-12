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
</script>

<template>
  <Select>
    <SelectTrigger>
      <SelectValue placeholder="Je cherche ..." />
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
