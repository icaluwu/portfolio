<template>
  <section id="certificates" class="py-5 bg-light">
    <div class="container">
      <h2 class="text-center mb-4">My Certificates</h2>

      <!-- Sertifikat Umum -->
      <div class="row justify-content-center">
        <div v-for="(certificate, index) in certificates" :key="index" class="col-lg-4 col-md-6 col-sm-12 mb-4">
          <div class="card h-100 certificate-item text-center p-3" @click="openModal(index, 'general')">
            <img :src="certificate.image" :alt="certificate.title" class="certificate-img">
            <p class="mt-2 fw-bold">{{ certificate.title }}</p>
          </div>
        </div>
      </div>

      <!-- TOEFL Section -->
      <h3 class="text-center mt-5">TOEFL Certification</h3>
      <div class="row justify-content-center">
        <div class="col-md-6 text-center">
          <div class="card h-100 certificate-item p-3" @click="openModal(0, 'toefl')">
            <img :src="toefl.image" :alt="toefl.title" class="certificate-img">
            <p class="mt-2 fw-bold">{{ toefl.title }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div v-if="selectedCertificate !== null" class="modal fade show d-block" tabindex="-1">
      <div class="modal-dialog modal-lg">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">{{ selectedData.title }}</h5>
            <button type="button" class="btn-close" @click="closeModal"></button>
          </div>
          <div class="modal-body text-center">
            <img :src="selectedData.image" class="img-fluid rounded shadow mb-3">
            <p>{{ selectedData.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal Background -->
    <div v-if="selectedCertificate !== null" class="modal-backdrop fade show" @click="closeModal"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      selectedCertificate: null,
      selectedCategory: null,
      certificates: [
        { title: "BNSP Junior Web Developer", image: new URL('@/assets/img/sert1.webp', import.meta.url).href },
        { title: "Python Essentials Certificate", image: new URL('@/assets/img/sert2.webp', import.meta.url).href },
        { title: "Dicoding Web Certificate", image: new URL('@/assets/img/sert3.webp', import.meta.url).href },
        { title: "Alibaba Cloud Computing Certificate", image: new URL('@/assets/img/sert4.webp', import.meta.url).href },
        { title: "Oracle & MySQL Certificate", image: new URL('@/assets/img/sert5.webp', import.meta.url).href },
        { title: "VueJS Workshop Certificate", image: new URL('@/assets/img/sert6.webp', import.meta.url).href }
      ],
      toefl: {
        title: "TOEFL Certification",
        image: new URL('@/assets/img/toefl.webp', import.meta.url).href
      }
    };
  },
  computed: {
    selectedData() {
      if (this.selectedCategory === "general") {
        return this.certificates[this.selectedCertificate];
      } else if (this.selectedCategory === "toefl") {
        return this.toefl;
      }
      return {};
    }
  },
  methods: {
    openModal(index, category) {
      this.selectedCertificate = index;
      this.selectedCategory = category;
    },
    closeModal() {
      this.selectedCertificate = null;
      this.selectedCategory = null;
    }
  }
};
</script>

<style scoped>
.card {
  min-height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.certificate-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 8px;
}

/* Hover effect */
.certificate-item {
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
}

.certificate-item:hover {
  transform: scale(1.05);
}

/* Modal Styling */
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
