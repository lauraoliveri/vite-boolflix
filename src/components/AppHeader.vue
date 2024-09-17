<script>
import { store } from '../store.js';
export default {
  data() {
    return { 
      
    }
  }
}
</script>

<template>
      <header>
          <nav class="navbar fixed-top">
            <div class="container-fluid">
              <a class="navbar-brand text-uppercase">Boolflix</a>
              <form @submit.prevent=""class="d-flex" role="search">
                <input v-model="store.SearchMovie" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button type="submit" class="btn btn-dark">Search</button>
              </form>
            </div>
          </nav>
      </header>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/variables' as *;

a {
  color: red;
  padding: 10px;

  :hover {
    color: rgb(255, 255, 255);
  }
}

nav {
  background-color: black;
}
</style>
