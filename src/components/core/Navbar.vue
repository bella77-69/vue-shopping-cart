<script>
import {mapGetters} from "vuex"
export default {
    name: "Navbar",
    computed: {
    ...mapGetters([
      'cartQuantity'
    ])
  },
  created() {
    this.$store.dispatch("getCartItems");
  }
}
</script>

<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a
          role="button"
          class="navbar-burger burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div id="navbarBasicExample" class="navbar-menu">
        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <router-link to="/inventory" class="button is-primary">
               <strong> Inventory</strong>
              </router-link>
              <router-link to="/cart"  class="button is-warning">   <p>
    Total cart items:
    <span> {{cartQuantity}}</span> </p>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>

<style scoped>
  .navbar {
    background-color:#047ffb;
  }
  .navbar-item {
    margin-right: 10px;
  }
  .navbar-item span {
    font-weight: bold;
  }
  .navbar-item button {
    margin-right: 10px;
  }
  .navbar-item button:last-child {
    margin-right: 0;
  }
  .navbar-item button i {
    font-size: 1.5rem;
  }
  .navbar-item button i:hover {
    cursor: pointer;
  }
  .navbar-item button i:active {
    transform: scale(1.1);
  }
</style>