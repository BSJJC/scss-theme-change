<script setup lang="ts">
import { ref } from "vue"

// init theme mode
let themeMode = ref("light");

if (document.documentElement.getAttribute("class")) {
  themeMode.value = document.documentElement.getAttribute("class") as string;
}
else {
  document.documentElement.setAttribute("class", "light");
}


const themeChange = (newTheme: string): void => {
  console.log(newTheme);

  document.documentElement.setAttribute("class", newTheme.toString());

  themeMode.value = newTheme
}

const themeSwitch = (): void => {
  themeMode.value === "light"
    ? themeChange("dark")
    : themeChange("light")


}

</script>

<template>
  <div class="container">
    <h1 class="title">theme now: {{ themeMode }}</h1>
    <button @click="themeSwitch">switch theme</button>
  </div>
</template>