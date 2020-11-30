<template>
  <div>
    <h2>HOME</h2>
    <router-link to="/todos">todos</router-link>
    <Preloader/>
  </div>
</template>

<script>
import Preloader from "@/components/Preloader";

export default {
  name: "Home",
  components: {
    Preloader

  }
}
</script>

<style scoped>

</style>
