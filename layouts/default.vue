<template>
<div>
<header>
      <headers/>
</header>
<between class="between">
  <Nuxt />
</between>
  <footer>
        <footers/>
  </footer>
</div>
</template>
<script>
import headers from "../components/header.vue"
import footers from "../components/footer.vue"
export default {
  components:{
    headers,footers
  }
}
</script>
<style>
.between{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
</style>
