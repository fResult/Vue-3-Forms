<template>
  <label v-if="label">{{ label }}</label>
  <select
    value="modelValue"
    class="field"
    v-bind="{
      ...$attrs,
      onChange: $event => $emit('update:modelValue', $event.target.value)
    }"
  >
    <option
      v-for="option in options"
      :value="option"
      :key="option"
      :selected="option === modelValue"
    >
      {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'BaseSelect',
  props: {
    modelValue: {
      type: [String, Number],
      default: ''
    },
    label: {
      type: String,
      default: ''
    },
    options: {
      type: Array,
      required: true
    }
  }
}
</script>
