<template>
   <div class="h-1/2 lg:h-screen bg-gradient-to-t from-indigo-200 relative">
       <nav class="w-full fixed top-0 bg-white">
           <div class="container mx-auto py-5 flex justify-between items-center">
               <div class="flex items-center gap-2">
                <img class="w-8" src="/logo.png" alt="" />
                <span class="text-2xl text-indigo-900 font-bold">Markeys.</span>
               </div>
               <ul class="hidden md:flex space-x-10 text-gray-600 font-bold text-sm uppercase">
                  <li class="hover:text-gray-500" v-for="navItem in navItems" :key="navItem.text"><nuxt-link :to="navItem.link">{{navItem.text}}</nuxt-link></li>
               </ul>
              <img class="hidden md:block cursor-pointer w-5" src="/logo.png" alt="" />
              <div class="md:hidden cursor-pointer space-y-1 z-20" @click="toggleNavbar">
                  <div class="w-6 h-0.5 bg-black"></div>
                  <div class="w-6 h-0.5 bg-black"></div>
                  <div class="w-6 h-0.5 bg-black"></div>
              </div>
              <ul v-if="showNav" class="absolute top-0 left-0 w-full p-10 rounded-b-3xl space-y-10 bg-indigo-500">
                  <li class="text-white text-center" v-for="navItem in navItems" :key="navItem.text"><nuxt-link :to="navItem.link">{{navItem.text}}</nuxt-link></li>
              </ul>
           </div>
       </nav>
       <img class="absolute right-0 bottom-0 lg:left-0 mx-auto object-cover" src="/marquis.png" alt="" />
       <div class="hidden lg:block "></div>
   </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      showNav : false,
      navItems : [
        {text : 'Hompage', link : '/#'},
        {text : 'About me', link : '/#'},
        {text : 'Services', link : '/#'},
        {text : 'Works', link : '/#'},
        {text : 'Contact', link : '/#'},
      ]
    }
  },
  methods : {
    toggleNavbar(){
       this.showNav = !this.showNav
    }
  }
}
</script>
