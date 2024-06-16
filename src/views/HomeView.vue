<template>
  
  <div class="home">
    <BooksRegist title="Gestion de Libros"/>
  </div>
</template>

<script>
// @ is an alias to /src
import BooksRegist from '@/components/BooksRegist.vue'

export default {
  name: 'HomeView',
  components: {
    BooksRegist
  }
}

</script>

<style scoped>

</style>