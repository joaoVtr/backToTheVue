<template>
  <!-- <div
    :class="[
      'alert',
      {
        'alert-success': variant === 'success',
        'alert-danger': variant === 'danger',
      },
    ]"
  > -->
  <!-- <div :class="`alert alert-${variant}`"> -->
  <div :class="baseClass">
    <div class="margin-b">
      <slot />
    </div>
    <div style="display: flex; justify-content: space-around">
      {{ text }}
      <button @click="onClick()">X</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    variant: {
      type: String,
      default: "",
    },
    text: {
      type: String,
      default: "Seu formulário não foi enviado com sucesso",
    },
    test: {
      type: String,
      default: "",
    },
  },
  computed: {
    baseClass() {
      return ["alert", this.variant ? `alert-${this.variant}` : ""];
    },
  },
  methods: {
    onClick() {
      this.$emit("close");
      console.log("clicou");
    },
  },
};
</script>

<style scoped>
.margin-b {
  font-weight: bold;
  margin-bottom: 2px;
}
.alert {
  padding: 5px;
  width: 20%;
  margin: 4px auto;
  border-radius: 6px;
  color: gray;
  background-color: rgba(169, 169, 169, 0.377);
}
.alert-success {
  background-color: rgba(0, 128, 0, 0.767);
  color: white;
}
.alert-danger {
  background-color: rgba(128, 0, 0, 0.767);
  color: white;
}
</style>
