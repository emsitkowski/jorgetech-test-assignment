<template>
  <button class="bg-primary">{{ props.label }}</button>
</template>

<script setup>
const props = defineProps({
  label: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
button {
  font-family: "Poppins";
  font-size: 17px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 3.4px;
  line-height: 120%;
  min-height: 60px;
  padding: 24px 68px;
  color: #fff;
  border-radius: 12px;
}
</style>
