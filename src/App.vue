<template>
 <div class="h-screen font-sans antialiased text-gray-900 bg-gray-100">
   <div class="flex">
    <side-bar/>
    <div class="items-center flex-1">
      <nav-bar/>
      <main-content/>
    </div>
   </div>
 </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import SideBar from './components/SideBar.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
   NavBar,
   SideBar,
   MainContent
  }, 
  data(){
    return{
     
    }
  }
}
</script>

<style>

</style>
