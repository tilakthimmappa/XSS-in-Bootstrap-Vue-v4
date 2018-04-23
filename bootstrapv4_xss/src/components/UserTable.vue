<template>
  <div>
    <b-table striped hover :items="reversedMessage"></b-table>
  </div>
</template>

<script>

export default {
  name: 'UserTable',
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  computed: {
    reversedMessage: function () {
      return this.items
    }
  }
}
</script>

<style scoped>

</style>
