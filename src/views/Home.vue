<template>
  <div class="home">
    <Navbar/>
    <Navbar2/>
    <!-- <Dashboard/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue'
import Navbar2 from '@/components/Navbar2.vue'
// import Dashboard from '@/components/Dashboard.vue'

export default {
  name: 'Home',
  components: {
    Navbar,
    Navbar2,
    // Dashboard
  }
}
</script>