<script>
import HelloWorld from './components/HelloWorld.vue';
import {useRecipesStore} from "./stores/RecipesStore";
import { mapState } from 'pinia';
export default {
  data() {
    return{
      isMenuVisible: true
    }
  },
  computed: {
    ...mapState(useRecipesStore,{
      test: "test"
    })
  },
  methods: {
    toggleMenu(){
      this.isMenuVisible = !this.isMenuVisible
    },
    goToLogin(){
      this.$router.push('/login')
    }
  }
}
</script>
<template>
  <div class="flex flex-col h-screen justify-between">
    <div class="flex-1 flex flex-col overflow-hidden">
  <nav class="flex justify-between items-center bg-orange-400 p-4">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between  mx-auto gap-3 md:gap-4  p-4">
      <a href="#" class="flex items-center">
      <img src="./assets/logoSmakoowa.png" class="h-8 mr-3" alt="Flowbite Logo">
      <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">Smakoowa</span>
      </a>
        <div class="flex md:order-2" >
          <button @click="goToLogin" type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 text-center mr-3 md:mr-0 dark:bg-orange-600 dark:hover:bg-orange-700 dark:focus:ring-orange-800">Log in</button>
          <button  @click="toggleMenu" data-collapse-toggle="navbar-sticky" type="button" class="inline-flex items-center p-2 text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" aria-controls="navbar-sticky" aria-expanded="false">
          <span class="sr-only">Open main menu</span>
          <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
          </button>
        </div>
        <div >
        <div class="items-center justify-between w-full md:flex md:w-auto md:order-1" v-bind:class="{'hidden': isMenuVisible}"  id="navbar-sticky">
          <ul class="flex flex-col p-4 md:p-0 mt-4 font-medium border border-gray-100 rounded-lg bg-gray-50 w-100 md:flex-row md:space-x-8 md:mt-0 md:border-0 md:bg-white dark:bg-gray-200 md:dark:bg-orange-400 dark:border-orange-700">
            <li>
              <router-link to="/" class="block py-2 pl-3 pr-4 text-white rounded md:bg-transparent md:text-white-700 md:p-0 dark:hover:bg-orange-700 md:dark:text-white-500" aria-current="page">Home</router-link>
            </li>
            <li>
              <router-link to="/about" href="#" class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-white-700 md:p-0 md:dark:hover:text-white-500 dark:text-white dark:hover:bg-orange-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Recipes</router-link>
            </li>
            <li>
            <a href="#" class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-white-700 md:p-0 md:dark:hover:text-white-500 dark:text-white dark:hover:bg-orange-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Categories</a>
            </li>
            <li>
            <a href="#" class="block py-2 pl-3 pr-4 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:hover:text-white-700 md:p-0 md:dark:hover:text-white-500 dark:text-white dark:hover:bg-orange-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">Top Recipes</a>
            </li>
          </ul>
        </div>
        </div>
    </div>
  </nav>
  <main class="flex flex-col w-full bg-white overflow-x-hidden overflow-y-auto">
  <RouterView></RouterView>
  <footer class="h-10 bg-orange-400 mt-4">
      <div class="container mx-auto px-4">
        <p class="text-center text-white">Powered by Smakoowa Team 2023 Not all right reserved</p>
      </div>
    </footer> 
  </main>
  </div>
 
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
