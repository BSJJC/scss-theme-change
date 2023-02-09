<script lang="ts" setup>
import { ref, setDevtoolsHook } from "vue"

let themeNow = ref("");

// init theme
if (localStorage.getItem("data-theme")) {
  const settedTheme: string = localStorage.getItem("data-theme") as string;
  document.documentElement.setAttribute("data-theme", settedTheme)
  themeNow.value = settedTheme;
}
else {
  localStorage.setItem("data-theme", "light");
  document.documentElement.setAttribute("data-theme", "light");
}

const changTheme = (newTheme: string): void => {
  localStorage.setItem("data-theme", newTheme);
  document.documentElement.setAttribute("data-theme", newTheme);

  themeNow.value = newTheme;
}

const switchTheme = (): void => {
  themeNow.value === "light"
    ? changTheme("dark")
    : changTheme("light")
};
</script>

<template>
  <div class="container">
    <h1 class="title"> the theme now is : {{ themeNow }}</h1>
    <button @click="switchTheme">Switch Theme</button>
    <h1 class="test">TEST</h1>
  </div>
</template>

<style lang="scss">

</style>