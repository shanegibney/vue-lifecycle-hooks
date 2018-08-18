<template lang="html">
  <div>
    <h1>{{ title }}</h1>
    <button @click="alterTitle()">Change title</button>
    <h2> <a href="">Return to repo</a> </h2>
  </div>
</template>

<script>
export default {
  name: 'Child',
  data () {
    return {
      title: 'Old title'
    }
  },
  methods: {
    alterTitle () {
      this.title = 'Much improved title'
    }
  },
  beforeCreate () {
    alert('beforeCreate: before componet is created')
  },
  created () {
    alert('created: component created but not yet added to DOM')
  },
  beforeMount () {
    alert('beforeMount: before component is mounted to the DOM but when it has been created')
  },
  mounted () {
    alert('mounted: after component is mounted to the DOM. This doesn\'t work for me')
  },
  beforeUpdate () {
    alert('beforeUpdate: before data is changed if it is about to change')
  },
  updated () {
    alert('updated: after data has been changed')
  },
  beforeDestroy () {
    alert('beforeDestroy: before component is destroyed')
  },
  destroy () {
    alert('destroy: after component has been destroyed')
  }
}
</script>

<style lang="css" scoped>
h1 {
  color: lightblue;
}
</style>
