<template>
  <header class="page-header">
  <nav class="menu">
    <h2>Navigation</h2>

  </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props:{
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.page-header{
  
  margin: 0px;
  border:dotted Darkred;
}
</style>
