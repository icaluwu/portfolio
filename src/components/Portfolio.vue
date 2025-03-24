<template>
  <section id="portfolio" class="portfolio-section py-5">
    <div class="container">
      <h2 class="section-title text-center">My Portfolio</h2>
      <p class="text-center text-muted">Here are some of my projects</p>

      <div class="row justify-content-center">
        <div v-for="(project, index) in projects" :key="index" class="col-lg-3 col-md-4 col-sm-6 mb-4 d-flex align-items-stretch">
          <div class="portfolio-item w-100" @click="openModal(index)">
            <img :src="project.image" :alt="project.title" class="img-fluid rounded shadow">
            <div class="overlay">
              <h4 class="text-white text-center">{{ project.title }}</h4>
            </div>
          </div>
        </div>
      </div>

      <!-- Modal -->
      <div v-if="selectedProject !== null" class="modal fade show d-block" tabindex="-1">
        <div class="modal-dialog modal-lg">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title">{{ projects[selectedProject].title }}</h5>
              <button type="button" class="btn-close" @click="closeModal"></button>
            </div>
            <div class="modal-body">
              <img :src="projects[selectedProject].image" class="img-fluid rounded mb-3">
              <p>{{ projects[selectedProject].description }}</p>
              <a :href="projects[selectedProject].link" target="_blank" class="btn btn-primary">
                View Project
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Modal Background -->
      <div v-if="selectedProject !== null" class="modal-backdrop fade show" @click="closeModal"></div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      selectedProject: null,
      projects: [
        {
          title: "L4Feer Website",
          image: "/src/assets/img/project1.webp",
          description: "An E-Commerce Restaurant Website using CodeIgniter3.",
          link: "https://github.com/icaluwu/Codeigniter3-Restaurant"
        },
        {
          title: "VieGroup Website",
          image: "/src/assets/img/project4.webp",
          description: "A Static Website fully deployed using Alibaba ECS and VueJS.",
          link: "https://viegroup.my.id"
        },
        {
          title: "Victovia Template",
          image: "/src/assets/img/project2.webp",
          description: "A static company website built with Vue.js, Bootstrap.",
          link: "https://github.com/icaluwu/Victovia"
        },
        {
          title: "Luxoria Interiors",
          image: "/src/assets/img/project3.webp",
          description: "An E-Commerce Furniture using CodeIgniter3, PHP and MySQL.",
          link: "http://luxorainteriors.unaux.com/?i=1"
        }
      ]
    };
  },
  methods: {
    openModal(index) {
      this.selectedProject = index;
    },
    closeModal() {
      this.selectedProject = null;
    }
  }
};
</script>

<style scoped>
.portfolio-section {
  background: #f8f9fa;
}

.section-title {
  font-size: 2rem;
  font-weight: bold;
}

.portfolio-item {
  position: relative;
  cursor: pointer;
  overflow: hidden;
  border-radius: 8px;
  transition: transform 0.3s ease-in-out;
}

.portfolio-item img {
  width: 100%;
  height: auto;
}

.portfolio-item:hover img {
  transform: scale(1.1);
}

.overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 123, 255, 0.8);
  padding: 10px;
  text-align: center;
}

.modal-content {
  border-radius: 8px;
}

.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1040;
}
</style>
