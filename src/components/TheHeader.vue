<template>
  <header class="header">
    <h2 v-if="$slots.title">
      <slot name="title" />
    </h2>
    <slot name="description" />
  </header>
</template>

<script>
export default {
  mounted() {
    console.log(this.$slots);
  },
};
</script>

<style>
.header {
  background: #000;
  color: #fff;
}
</style>
