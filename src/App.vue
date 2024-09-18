<script>
/* 
  Per importare ed utilizzare un componente dentro un altro devo SEMPRE seguire questi 3 passi:
  1) Importazione del componente
  2) Dichiarazione del componente
  3) Utilizzo del componente
*/
// 1) Importazione del componente
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import SingleMovie from './components/SingleMovie.vue';



export default {
  data() {
    return { 
      store
    }
  },
  // 2) Dichiarazione del componente
  components: {
    AppHeader,
    AppMain,
    SingleMovie
  },
  methods: {
      performSearch() {
        axios
        .get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'e1d9f6392b861b67ce93fbe118964004',
          query: ''
          
        }
        .catch((err) => {
          console.error(err);
        })
      })

        
    }
  }
}

</script>

<template>
  <div>
    <!-- 3) Utilizzo del componente -->
    <AppHeader  @search="performSearch()" />
    
    <main>
     <AppMain/>

     <SingleMovie/>

    </main>
  </div>
</template>

<style lang="scss">
@use 'assets/scss/main' as *;
// Import all of Bootstrap's CSS
@import "bootstrap/scss/bootstrap";
</style>
