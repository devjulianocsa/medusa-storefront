<script setup lang="ts">
import { useRoute } from 'vue-router'
import Medusa from "@medusajs/medusa-js"

const route = useRoute()
const MEDUSA_BACKEND_URL = process.env.VUE_APP_MEDUSA_BACKEND_URL || 'default_url'
const medusa = new Medusa({ baseUrl: MEDUSA_BACKEND_URL, maxRetries: 3 })

medusa.productCategories.list()
.then(({ product_categories, limit, offset, count }) => {
  console.log(product_categories.length);
})

</script>

<template>
  <section >
    <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
      <header class="text">
        <h2 class="text-xl font-bold text-gray-900 sm:text-3xl">Categorias</h2>
  
        <p class="mx-auto mt-4 max-w-md text-gray-500">
          
Navegue pelas coleções refinadas da KaroB e encontre sua próxima peça favorita, Descubra a elegância e o estilo atemporal que você procura!
        </p>
      </header>
      
      <ul class="flex justify-center items-center h-screen gap-4 sm:grid-cols-2 lg:grid-cols-4">
  <li class="relative">
    <a href="#" class="group block overflow-hidden">
      <img
        src="/vestido-nude.png"
        alt=""
        class="h-[350px] w-full object-cover transition duration-500 group-hover:scale-105 sm:h-[450px]"
      />
      <div class="absolute inset-0 bg-white bg-opacity-70 flex justify-center items-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
        <h3 class="text-lg text-gray-700 text-center">
          Vestidos
        </h3>
      </div>
    </a>
  </li>
  
  <li class="relative">
    <a href="#" class="group block overflow-hidden">
      <img
        src="/blusa-basica.png"
        alt=""
        class="h-[350px] w-full object-cover transition duration-500 group-hover:scale-105 sm:h-[450px]"
      />
      <div class="absolute inset-0 bg-white bg-opacity-70 flex justify-center items-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
        <h3 class="text-lg text-gray-700 text-center">
          Blusas
        </h3>
      </div>
    </a>
  </li>
  
  <li class="relative">
    <a href="#" class="group block overflow-hidden">
      <img
        src="/saia-bege.png"
        alt=""
        class="h-[350px] w-full object-cover transition duration-500 group-hover:scale-105 sm:h-[450px]"
      />
      <div class="absolute inset-0 bg-white bg-opacity-70 flex justify-center items-center opacity-0 group-hover:opacity-100 transition-opacity duration-300">
        <h3 class="text-lg text-gray-700 text-center">

          Saias
        </h3>
      </div>
    </a>
  </li>
</ul>


      
    </div>
  </section>
</template>


