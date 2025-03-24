<template>
  <section id="contact" class="py-5">
    <div class="container">
      <h2 class="text-center mb-4">Contact Me</h2>

      <!-- Social Media Buttons -->
      <div class="text-center mb-4">
        <a :href="whatsappLink" target="_blank" class="btn btn-success me-2">
          <i class="fab fa-whatsapp"></i> WhatsApp
        </a>
        <a :href="githubLink" target="_blank" class="btn btn-dark me-2">
          <i class="fab fa-github"></i> GitHub
        </a>
        <a :href="linkedinLink" target="_blank" class="btn btn-primary">
          <i class="fab fa-linkedin"></i> LinkedIn
        </a>
      </div>

      <!-- Contact Form -->
      <div class="row justify-content-center">
        <div class="col-md-6">
          <form @submit.prevent="sendEmail">
            <div class="mb-3">
              <label for="name" class="form-label">Your Name</label>
              <input type="text" id="name" v-model="form.name" class="form-control" required>
            </div>
            <div class="mb-3">
              <label for="email" class="form-label">Your Email</label>
              <input type="email" id="email" v-model="form.email" class="form-control" required>
            </div>
            <div class="mb-3">
              <label for="message" class="form-label">Message</label>
              <textarea id="message" v-model="form.message" class="form-control" rows="4" required></textarea>
            </div>
            <button type="submit" class="btn btn-primary w-100">
              <i class="fas fa-paper-plane"></i> Send Message
            </button>
          </form>
        </div>
      </div>

      <!-- Alert Message -->
      <div v-if="alertMessage" class="alert mt-3 text-center" :class="alertType">
        {{ alertMessage }}
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  data() {
    return {
      whatsappLink: "https://wa.me/6287896542511", 
      githubLink: "https://github.com/icaluwu",
      linkedinLink: "https://linkedin.com/in/vaickal-teuku-865b7123a/",
      form: {
        name: "",
        email: "",
        message: ""
      },
      alertMessage: "",
      alertType: ""
    };
  },
  methods: {
    sendEmail() {
      const serviceID = "service_icaluwu"; 
      const templateID = "template_eu3nuze"; 
      const publicKey = "Z98vsBcWFRzIQqJBC"; 
      emailjs
        .send(serviceID, templateID, this.form, publicKey)
        .then(() => {
          this.alertMessage = "Email sent successfully!";
          this.alertType = "alert-success";
          this.form.name = "";
          this.form.email = "";
          this.form.message = "";
        })
        .catch(() => {
          this.alertMessage = "Failed to send email. Please try again!";
          this.alertType = "alert-danger";
        });
    }
  }
};
</script>

<style scoped>
.btn {
  font-size: 1.2rem;
}

.alert {
  font-size: 1rem;
  padding: 10px;
  border-radius: 5px;
}
</style>
