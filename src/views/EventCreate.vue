<template>
  <div>
    <h1>Create Event</h1>
    <p>Name: {{ user.name }}</p>
    <p>Id: {{ user.id }}</p>
    <p>Local Prop: {{ localComputed.aaa }}</p>
    <h3>Categories</h3>
    <ul>
      <li v-for="category in categories" :key="category">
        {{ category }}
      </li>
    </ul>
  </div>
</template>

<script>

  import { mapState } from 'vuex'

  export default {
    computed: {
      localComputed() {
        return {aaa: 'something'}
      },
      ...mapState(['user','categories'])
    }
  }
</script>

<style lang="scss" scoped>

</style>
