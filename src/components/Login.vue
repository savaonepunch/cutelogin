<template>
  <div class="bg-image"></div>
  <div ref="loginContainer" class="login-container">
    <img ref="logo" class="logo" src="../assets/images/logo2.png" alt="Logo" />
    <div class="box">
      <h1 class="header">Welcome back!</h1>
      <p class="description">Enter your credentials to access your account.</p>
      <form class="login-form">
        <input type="text" id="email" placeholder="Enter your email" />
        <span class="fa-solid fa-envelope fa-lg email-span"></span>
        <input
          type="password"
          id="password"
          placeholder="Enter your password"
        />
        <span class="fa-solid fa-lock fa-lg password-span"></span>
        <button type="submit">Sign in</button>
      </form>
    </div>
    <p ref="forgotPassword" class="forgot-password">
      Forgot your password? <a href="#">Reset Password</a>
    </p>

    <i @click="showBg" ref="bgBtn" class="fa-solid fa-image fa-2xl bg-button"></i>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const bgBtn = ref();
const loginContainer = ref();
const forgotPassword = ref();
const logo = ref();

const showBg = () => {
    if (bgBtn.value.style.color !== "rgb(255, 255, 255)") {
        bgBtn.value.style.color = "rgb(255, 255, 255)";
        loginContainer.value.style.background = 'url(https://source.unsplash.com/random/1920x1080) no-repeat center center fixed';
        loginContainer.value.style.backgroundSize = 'cover';
        forgotPassword.value.style.color = 'white';
        logo.value.style.filter = "brightness(0) invert(1)";
    }
    else {
        bgBtn.value.style.color = "var(--blue)";
        loginContainer.value.style.background = '#f2fafe';
        forgotPassword.value.style.color = 'var(--gray)';
        logo.value.style.filter = "none";
    }
}

</script>
