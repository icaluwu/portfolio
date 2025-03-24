<template>
  <section id="about" class="about-section py-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6 text-center">
          <img src="@/assets/img/avatar.webp" alt="Ical's Profile" class="img-fluid rounded-circle shadow-lg profile-img">
        </div>
        <div class="col-lg-6">
          <h2 class="section-title">About Me</h2>
          <p class="text-muted">
            Hi, I'm <strong>Teuku Vaickal Rizki Irdian</strong>, a passionate Web Developer and Cloud Enthusiast. I specialize in building modern, scalable, and high-performance web applications using technologies like 
            <span class="highlight">Vue.js, CodeIgniter, MySQL, and Bootstrap</span>.
          </p>
          <p class="text-muted">
            With a strong background in <span class="highlight">full-stack development</span>, I have experience in both <span class="highlight">frontend and backend programming</span>, ensuring seamless and interactive user experiences.
          </p>
          <a href="#portfolio" class="btn btn-primary mt-4">View My Work</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  background-color: #f8f9fa;
}

.section-title {
  font-size: 2rem;
  font-weight: bold;
  color: #333;
}

.profile-img {
  max-width: 250px;
  border: 5px solid #007bff;
}

.text-muted {
  font-size: 1.1rem;
  line-height: 1.6;
}

.highlight {
  color: #007bff;
  font-weight: bold;
}

.gpa-chart-container {
  position: relative;
  height: 300px;
  width: 100%;
  margin-top: 20px;
}
</style>
