<script setup lang="ts">
defineProps<{
  modelValue: string
}>()


defineEmits<{
  'update:modelValue': [
    value: string
  ]
}>()
</script>


<template>
  <input
    class="filter-input"
    type="search"

    :value="modelValue"

    placeholder="Filter rockets..."

    @input="
      $emit(
        'update:modelValue',
        ($event.target as HTMLInputElement).value
      )
    "
  >
</template>


<style scoped>
.filter-input {
  width: 100%;

  padding:
    13px 16px;
  color:black;
  border:
    1px solid #f7f5f5;

  border-radius: 8px;

  background: white;

  font-size: 15px;
}

.filter-input:focus {
  border-color: #e1e0e0;
}

@media (max-width: 640px) {
  .filter-input {
    padding: 11px 13px;

    font-size: 13px;
  }
}
</style>
