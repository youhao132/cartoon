<template>
  <Header />
  <Lunbo />
  <Kind />
  <Hot />
</template>

<script>
import Header from "../components/Header.vue";
import Lunbo from "../components/Lunbo.vue"
import Kind from "../components/Kind.vue"
import Hot from "../components/Hot.vue"
export default {
  components: { 
    Header,
    Kind,
    Lunbo,
    Hot,
  }
}
</script>

<style>

</style>