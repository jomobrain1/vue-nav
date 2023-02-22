<template>
  <div class="bg-black text-grey-100 py-5  md:py-4 px-10 md:flex justify-between items-center">
   <h1 class="text-xl my-2 text-white font-bold">jomobrain1</h1>
   <span @click="menuOpen()" class="absolute md:hidden right-6 top-7 cursor-pointer ">
    <span class="text-white text-xl">&#9776;</span>
   </span>

   <ul
    class="py-5 md:py-0 px-10 md:p-0 md:flex md:items-center md:static absolute bg-black md:w-auto w-full top-14 duration-700 ease-in " 
    :class="[open? 'left-0':'left-[-100%]']"
    >
    
    <li class="my-4 md:my-1 md:mx-3" v-for="link in links">
        <a :href="link.link" class="text-l text-white hover:text-green-400">{{ link.name }}</a>
    </li>
    
    <StartButton>
      Get Started
    </StartButton>
  </ul>
  </div>

</template>

<script>
import { ref } from 'vue';
import StartButton from './StartButton.vue';


export default {
    setup() {
      
      let open=ref(false)
      function menuOpen(){
        open.value=!open.value
      }
        let links = [
            { name: "Home", link: "#" },
            { name: "About", link: "#" },
            { name: "Contact", link: "#" },
            { name: "Services", link: "#" },
        ];
        return { links,open,menuOpen };
    },
    components: { StartButton }
};
</script>

<style lang="scss" scoped></style>
