<template>
  <div>
    <input type="email" v-model="email">
    <button @click="enter()">{{ buttonLabel }}</button>
    <div v-if="!email.includes('@')">Twój email jest nieprawidlowy!</div>
    <div v-else-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
  </div>
</template>

<script>
export default {
  props: {buttonLabel: String},
  data() {
    return {
      email: ''
    }
  },
  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  }
}
</script>

<style scoped>

</style>