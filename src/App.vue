<script setup lang="ts">
import Logo from "./components/Logo.vue";
import MidnightFrost from "./components/MidnightFrost.vue";
import MidnightFrostLogo from "./components/MidnightFrostLogo.vue";
import GoGoLogo from "./components/GoGoLogo.vue";
import TheBasicLogo from "./components/TheBasicLogo.vue";
</script>

<template>
  <div class="main-app">
    <div class="split left">
      <MidnightFrost />
      <div class="centered">
        <MidnightFrostLogo light />
      </div>
    </div>

    <div class="split center">
      <div class="centered">
        <GoGoLogo light />
      </div>
    </div>

    <div class="split right">
      <div class="centered">
        <TheBasicLogo light />
      </div>
    </div>
  </div>
  <Logo light class="logo" />
</template>

<style scoped>
.logo {
  position: absolute;
  bottom: 40px;
  right: 20px;
  width: 40%;
  height: auto;
  min-width: 300px;
  z-index: 99;
}

.split {
  height: 100%;
  position: fixed;
  z-index: 0;
  top: 0;
  overflow-x: hidden;
  padding-top: 20px;
}

/* Control the left side */
.left {
  transition: box-shadow 0.3s;
  left: -16%;
  width: 49%;
  z-index: 1;
  background-color: #111;
  transition: var(--transition-length) linear;
  transform: skewX(-10deg);
}

/* Control the right side */
.right {
  transition: box-shadow 0.3s;
  right: -16%;
  width: 43%;
  background-color: #242424;
  transition: var(--transition-length) linear;
  transform: skewX(-10deg);
}

/* Control the center */
.center {
  transition: box-shadow 0.3s;
  left: 33.3%;
  width: 40%;
  z-index: 1;
  background-color: palevioletred;
  transform: skewX(-10deg);
  transition: var(--transition-length) linear;
}

.left:hover,
.right:hover,
.center:hover {
  /* box-shadow: 0 0 110px rgb(33 33 33 / 80%); */
  transform: skewX(-10deg) scale(1.1);
  z-index: 2;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

div.left > div.centered {
  left: 65%;
}

div.right > div.centered {
  left: 33%;
  padding: 30px;
}

@media only screen and (max-width: 600px), (hover: none), (hover: on-demand) {
  #app {
    padding: 0;
  }

  .main-app {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    align-items: center;
    height: 100vh;
    width: 100vw;
    padding: 0;
  }

  .split {
    position: relative;
    display: block;
  }

  .center,
  .left,
  .right {
    transform: skewX(0);
    width: 100%;
    left: 0;
    height: 33.3%;
    transition: var(--transition-length) linear;
  }

  .left,
  .right {
    padding-left: 0;
    transition: var(--transition-length) linear;
  }

  .left {
    left: 0;
  }
  .right {
    right: 0;
  }

  .left:hover,
  .right:hover,
  .center:hover {
    box-shadow: 0 0 110px rgb(33 33 33 / 80%);
    transform: skewX(0deg) scale(1.1);
    z-index: 2;
  }

  div.left > div.centered,
  div.right > div.centered {
    padding: 0;
    left: 50%;
  }
}
</style>
