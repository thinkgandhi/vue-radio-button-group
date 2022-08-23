<template>
  <label :for="option">
    <input
      type="radio"
      :value="option"
      :id="option"
      @change="$parent.$emit('input', $event.target.value)"
      name="radio-input"
    />
    {{ option }}
  </label>
</template>

<script>
export default {
  props: {
    option: {
      required: true,
      type: String,
    },
  },
};
</script>

<style scoped>
label {
  cursor: pointer;
}
</style>