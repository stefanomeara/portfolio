<template>
  <Navbar/>
  <div class="content">
    <EatSleepCode/>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue"
import EatSleepCode from "./components/EatSleepCode.vue";

export default {
  name: "App",
  components: {
    EatSleepCode,
    Navbar
  }
}
</script>

<style>
@tailwind base;
@tailwind components;
@tailwind utilities;

.content {
  margin-top: 20px;
  margin-left: 170px !important;
  margin-right: 170px !important;
  width: calc(100% - 340px);
}

@media only screen and (max-width: 900px) {
  .content {
    margin-left: 1.25rem !important;
    margin-right: 1.25rem !important;
    width: calc(100% - 2.5rem);
  }
}
</style>
