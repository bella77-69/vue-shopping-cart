<script>
import Navbar from './components/core/Navbar'
export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

<template>
  <div>
    <Navbar/>
    <div class="container mt-6">
      <div class="columns">
        <div class="column is-12 column--align-center">
          <router-view></router-view>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
html,
body {
  height: 100%;
  background: #d6e2ee;
}
</style>