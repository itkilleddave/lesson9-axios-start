<template>
  <div>
    <h1>Create Event</h1>
    <p>Name: {{ user.name }}</p>
    <p>Id: {{ user.id }}</p>
    <p>Local Prop: {{ localComputed.aaa }}</p>
    <h3>Categories ({{ catLength }})</h3>
    <p>Done ToDos: {{ doneToDos }}</p>
    <p>Active ToDos Count: {{ activeToDosCount }}</p>
    <!-- <p>{{ eventById(1) }}</p> -->
    <ul>
      <li v-for="category in categories" :key="category">
        {{ category }}
      </li>
    </ul>
  </div>
</template>

<script>

  import { mapState, mapGetters } from 'vuex'

  export default {
    computed: {
      // getEvent() {
      //   return this.$store.getters.eventById
      // },
      // catLength() {
      //   return this.$store.getters.catLength
      // },
      // doneToDos() {
      //   return this.$store.getters.doneToDos
      // },
      // activeToDosCount() {
      //   return this.$store.getters.activeToDosCount
      // },
      localComputed() {
        return {aaa: 'something'}
      },
      ...mapGetters(['catLength', 'doneToDos', 'activeToDosCount']),
      ...mapState(['user','categories'])
    }
  }
</script>

<style lang="scss" scoped>

</style>
