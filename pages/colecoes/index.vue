<script setup lang="ts">
import { ref } from 'vue';
import Medusa from "@medusajs/medusa-js"

const MEDUSA_BACKEND_URL = process.env.VITE_MEDUSA_BACKEND_URL || 'http://localhost:3000';
const medusa = new Medusa({ baseUrl: MEDUSA_BACKEND_URL, maxRetries: 3 })
medusa.collections.list()
.then(({ collections, limit, offset, count }) => {
  console.log(collections.length);
})

</script>

<template>
  <section>
    <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 sm:py-12 lg:px-8">
      <header class="text-">
        <h2 class="text-xl font-bold text-gray-900 sm:text-3xl">Nova Coleção</h2>
  
        <p class="mx-auto mt-4 max-w-md text-gray-500">
          Apresentamos a coleção "Rose" da KaroB: uma seleção elegante e atemporal de peças cuidadosamente criadas para elevar seu guarda-roupa com sofisticação e estilo. Descubra o poder da moda com a KaroB.
        </p>
      </header>
  
      <ul class="mt-8 grid grid-cols-1 gap-4 lg:grid-cols-3">
        <li>
          <a href="#" class="group relative block">
            <img
            src= "/blusa-basica.png"
              alt=""
              class="aspect-square w-full object-cover transition duration-500 group-hover:opacity-90"
            />
  
            <div class="absolute inset-0 flex flex-col items-start justify-end p-6">
              <h3 class="text-xl font-medium text-white">Blusa Básica</h3>
  
              <span
                class="mt-1.5 inline-block bg-black px-5 py-3 text-xs font-medium uppercase tracking-wide text-white"
              >
                Compre Agora
              </span>
            </div>
          </a>
        </li>
  
        <li>
          <a href="#" class="group relative block">
            <img
              src="/saia-bege.png"
              alt=""
              class="aspect-square w-full object-cover transition duration-500 group-hover:opacity-90"
            />
  
            <div class="absolute inset-0 flex flex-col items-start justify-end p-6">
              <h3 class="text-xl font-medium text-white">Saia</h3>
  
              <span
                class="mt-1.5 inline-block bg-black px-5 py-3 text-xs font-medium uppercase tracking-wide text-white"
              >
                Compre Agora
              </span>
            </div>
          </a>
        </li>
  
        <li class="lg:col-span-2 lg:col-start-2 lg:row-span-2 lg:row-start-1">
          <a href="#" class="group relative block">
            <img
              src="/vestido-nude.png"
              alt=""
              class="aspect-square w-full object-cover transition duration-500 group-hover:opacity-90"
            />
  
            <div class="absolute inset-0 flex flex-col items-start justify-end p-6">
              <h3 class="text-xl font-medium text-white">Vestido Nude</h3>
  
              <span
                class="mt-1.5 inline-block bg-black px-5 py-3 text-xs font-medium uppercase tracking-wide text-white"
              >
                Compre Agora
              </span>
            </div>
          </a>
        </li>
      </ul>
    </div>
  </section>
</template>
