<template>
  <section id="questions" class="py-5 bg-light">
    <div class="container">
      <h2 class="text-center mb-4">Frequently Asked Questions</h2>

      <div class="accordion" id="faqAccordion">
        <!-- Question 1 -->
        <div class="accordion-item">
          <h2 class="accordion-header">
            <button class="accordion-button" :class="{ collapsed: activeQuestion !== 1 }" @click="toggleDropdown(1)">
              Can I hire you for a project?
            </button>
          </h2>
          <div v-show="activeQuestion === 1" class="accordion-collapse collapse show">
            <div class="accordion-body">
              Yes, feel free to <a class="link-body-emphasis link-offset-2 link-underline link-underline-opacity-0" href="#contact">contact me</a>!
            </div>
          </div>
        </div>

        <!-- Question 2 -->
        <div class="accordion-item">
          <h2 class="accordion-header">
            <button class="accordion-button" :class="{ collapsed: activeQuestion !== 2 }" @click="toggleDropdown(2)">
              What technologies do you use?
            </button>
          </h2>
          <div v-show="activeQuestion === 2" class="accordion-collapse collapse show">
            <div class="accordion-body">
              Vue.js, Alibaba ECS, CodeIgniter, Bootstrap, etc.
            </div>
          </div>
        </div>

        <!-- Question 3 -->
        <div class="accordion-item">
          <h2 class="accordion-header">
            <button class="accordion-button" :class="{ collapsed: activeQuestion !== 3 }" @click="toggleDropdown(3)">
              What is your GPA now?
            </button>
          </h2>
          <div v-show="activeQuestion === 3" class="accordion-collapse collapse show">
            <div class="accordion-body">
              <canvas id="gpaChart"></canvas>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Chart from "chart.js/auto";

export default {
  data() {
    return {
      activeQuestion: null,
      gpaChart: null
    };
  },
  methods: {
    toggleDropdown(question) {
      this.activeQuestion = this.activeQuestion === question ? null : question;

      if (question === 3 && this.activeQuestion === 3) {
        this.$nextTick(() => {
          this.renderGpaChart();
        });
      }
    },
    renderGpaChart() {
      if (this.gpaChart) {
        this.gpaChart.destroy();
      }
      const ctx = document.getElementById("gpaChart");
      this.gpaChart = new Chart(ctx, {
        type: "line",
        data: {
          labels: ["Semester 1", "Semester 2", "Semester 3", "Semester 4", "Semester 5"],
          datasets: [
            {
              label: "GPA",
              data: [4.00, 4.00, 3.83, 3.70, 3.87], 
              borderColor: "blue",
              backgroundColor: "rgba(0, 0, 255, 0.1)",
              borderWidth: 2
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            y: {
              beginAtZero: false,
              suggestedMin: 3.0,
              suggestedMax: 4.0
            }
          }
        }
      });
    }
  }
};
</script>

<style scoped>
.accordion-button {
  font-weight: bold;
  cursor: pointer;
}

.accordion-body {
  font-size: 1rem;
}

canvas {
  width: 100% !important;
  height: 300px !important;
}
</style>
