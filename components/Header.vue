<template>
  <b-navbar toggleable="lg">
    <b-container>
      <b-navbar-brand href="#"><img src="/logo.png" alt=""></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"><i class="fas fa-bars"></i></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="#">Home</b-nav-item>
          <b-nav-item href="#">Project</b-nav-item>
          <b-nav-item href="#">About</b-nav-item>
          <b-nav-item href="#">Contact Us</b-nav-item>
          <b-nav-form>
            <b-form-input size="sm"></b-form-input>
            <!-- <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button> -->
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-container>
  </b-navbar>
</template>

