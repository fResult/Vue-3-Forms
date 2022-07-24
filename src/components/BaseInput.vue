<template>
  <label v-if="label">{{ label }}</label>
  <input
    class="field"
    :placeholder="label"
    :value="modelValue"
    @input="$emit('update:modelValue', $event?.target?.value)"
    v-bind="{ ...$attrs, type: $attrs.type ? $attrs.type : 'text' }"
  />
</template>

<script>
export default {
  name: 'BaseInput',
  props: {
    modelValue: {
      type: [String, Number],
      default: ''
    },
    label: {
      type: String,
      default: ''
    }
  }
}
</script>
