<template>
  <b-navbar toggleable="lg">
    <b-container>
      <b-navbar-brand href="#"><img src="/logo.png" alt=""></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"><i class="fas fa-bars"></i></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item to="/">Home</b-nav-item>
          <b-nav-item to="/project">Project</b-nav-item>
          <b-nav-item to="/about">About</b-nav-item>
          <b-nav-item to="/contact">Contact Us</b-nav-item>
          <!-- <b-nav-form>
            <form @submit.prevent="noop">
              <b-form-input v-model="search" size="sm" @keyup.enter.native="onEnter"></b-form-input>
            </form>
          </b-nav-form> -->
        </b-navbar-nav>
      </b-collapse>
    </b-container>
  </b-navbar>
</template>


<script>

export default {
  data() {
    return {
      search: "",
    }
  },
  methods: {
    onEnter(){
      this.$router.push({ path: `/project?search=${this.search}` })
    },
    noop () {
      // do nothing ?
    }
  }
}
</script>