<template>
  <div class="main">
  <div class="nav">
    <Nav/>
    </div>
  <div class="content">
  <router-view />

  </div>
  </div>
</template>

<script>
import Nav from './components/Nav.vue'

export default {
  name: 'App',
  components: {
    Nav
  }
}
</script>



<style scoped>
.main {
  display: flex;
  
  
}
.content {
  flex: 1 0 auto;
}
.nav {
  flex: 0 1 176px;
  
}


</style>
