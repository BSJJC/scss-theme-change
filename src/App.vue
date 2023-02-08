<script lang="ts" setup>
import { ref } from "vue";

let themeNow = ref("light");
</script>

<template>
  <div class="container">
    <h1>the theme now is: {{ themeNow }} </h1>

    <button>theme switch</button>
  </div>
</template>

<style lang="scss">

</style>