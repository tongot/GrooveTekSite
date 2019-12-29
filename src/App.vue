<template>
  <v-app class="orange lighten-5">
   <Navbar/>
    <v-content class="mx-4">
      <transition>
      <router-view></router-view>      
      </transition>
    </v-content>
    <Footer/>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'
import Footer from '@/components/footer'

export default {
  name: 'App',
  components:{Navbar,Footer},
  data: () => ({
    //
  }),
};
</script>
<style scoped>
 .v-enter-active{
   animation:bounceIn 2s;
 }
 .v-leave-active{
   animation:bounceIn 1s reverse;
 }
 @keyframes bounceIn{
    0%{
      transform: scale(0.1);
      opacity: 0;
    }
     
    100%{
      transform: scale(1);
      opacity: 1;
    }
 }
</style>