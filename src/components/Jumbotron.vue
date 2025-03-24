<template>
  <header class="jumbotron d-flex align-items-center">
    <div class="container text-center text-white">
      <h1 class="display-4 fw-bold">Hi, I'm Vaickal</h1>
      <p class="lead typing-text">Junior Web Developer |  Undergraduate Student</p>
      <a href="#portfolio" class="btn btn-light mt-3 px-4 py-2 fw-bold">View My Work</a>
    </div>
  </header>
</template>

<style scoped>
.jumbotron {
  height: 100vh;
  background: linear-gradient(to right, #007bff, #6610f2);
  display: flex;
  justify-content: center;
  text-align: center;
}

.typing-text {
  font-size: 1.5rem;
  font-weight: bold;
  white-space: nowrap;
  overflow: hidden;
  border-right: 3px solid white;
  width: 0;
  animation: typing 3s steps(40, end) forwards, blink 0.8s infinite;
}

@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

@keyframes blink {
  50% { border-color: transparent; }
}
</style>
