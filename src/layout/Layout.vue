<template>
    <div v-if="is_logged_in" class="main-page d-flex">
      <NavBar v-if="is_shown" @toggle_nav_bar="toggle_nav_bar" @logout="logout" />
      <!-- <div class="row col-10 h-100 d-flex no-align"> -->
      <div class="col-12">
        <TopBar v-if="is_logged_in" @toggle_nav_bar="toggle_nav_bar" />
        <div class="page-body scrollable-page">
          <router-view/>
        </div>
      </div>
    </div>
    <!-- login page -->
    <div v-else class="main-page d-flex">
      <UserLogin @login="login" />
    </div>
  </template>
  
  <script>
  import NavBar from '@/components/Navbar.vue';
  import TopBar from '@/components/TopBar.vue';
  import UserLogin from '@/views/Login.vue'
  
  
  export default {
    name: 'PageLayout',
    data() {
      return {
        is_logged_in: false,
        is_shown: false,
      }
    },
    computed: {
  
},
    components: { NavBar, TopBar, UserLogin},
    methods: {
      toggle_nav_bar(){
        this.is_shown = !this.is_shown
      },
      login(){
        this.is_logged_in = true
        //use local storage
        localStorage.setItem("is_logged_in", this.is_logged_in)
        this.$router.push('/home')

      },
      logout(){
        this.is_logged_in = false
        localStorage.setItem("is_logged_in", this.is_logged_in)
        this.is_shown = false
      }
    },
    mounted(){
      this.is_logged_in = localStorage.getItem("is_logged_in")
    }
  }
  </script>