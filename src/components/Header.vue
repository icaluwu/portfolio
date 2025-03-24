<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container">
      <a class="navbar-brand fw-bold" href="#">IcalUwU</a>
      <button 
        class="navbar-toggler" 
        type="button" 
        @click="toggleNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" :class="{ 'show': isNavbarOpen }" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link" href="#skills" @click="closeNavbar">Skills</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#about" @click="closeNavbar">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#portfolio" @click="closeNavbar">Portfolio</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#certificates" @click="closeNavbar">Certificates</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#questions" @click="closeNavbar">Questions</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contact" @click="closeNavbar">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isNavbarOpen: false,
    };
  },
  methods: {
    toggleNavbar() {
      this.isNavbarOpen = !this.isNavbarOpen;
    },
    closeNavbar() {
      this.isNavbarOpen = false;
    },
  },
};
</script>

<style scoped>
.navbar {
  padding: 10px 0;
}

.navbar-brand {
  font-size: 1.5rem;
}

.navbar-nav .nav-link {
  font-size: 1.1rem;
  transition: color 0.3s;
}

.navbar-nav .nav-link:hover {
  color: #007bff;
}

.collapse {
  transition: max-height 0.3s ease-in-out;
}
</style>
