<template>
  <section>
    <h2>{{ username }}</h2>
    <h2> {{ age }}</h2>
  </section>
  <button @click="$emit('delete', id)">Delete</button>
</template>

<script>
export default {
  emits: ['delete'],
  props: {
    id: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    },
    age: {
      type: Number,
      required: true
    }
  },
  data() {
  },
  methods: {

  },
}
</script>

<style>
section {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  color: #004658;
}
</style>