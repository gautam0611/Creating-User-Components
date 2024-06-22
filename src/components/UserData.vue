<template>
  <section>
    <form @submit.prevent="setData">
      <input type="text" placeholder="Your Name" v-model="enteredName">
      <input type="text" placeholder="Your Age" v-model="enteredAge">
      <button>Set a User</button>
    </form>
  </section>
</template>

<script>
export default {
  emits: ['set-data'],
  data() {
    return {
      enteredName: '',
      enteredAge: ''
    }
  },
  methods: {
    setData() {
      this.$emit('set-data', this.enteredName, this.enteredAge)
    }
  }

}
</script>