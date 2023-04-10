<script setup>
  import Modal from '../Modal.vue'
</script>

<template>
  <div class="col-span-6 lg:col-span-2 bg-white rounded-md p-5 lg:ml-4 mt-12 lg:mt-0 shadow-md h-fit">
    <h3 class="font-semibold text-xl mb-6 flex gap-2">Product Organization <img src="../../assets/icon/icon.svg" class="w-5 lg:w-6 -mt-2" alt="icon"/></h3>
    <label for="product-category" class="text-sm md:text-md lg:text-base">Product Category</label>
    <Modal />
    <label for="product-brand" class="text-sm md:text-md lg:text-base">Product Brand</label>
    <input type="text" placeholder="e.g., T-Shirt" class="block w-full border border-gray-500 px-3 py-2 mt-2 mb-8 rounded-md text-sm md:text-md lg:text-base" id="product-brand">
    <label for="collections" class="text-sm md:text-md lg:text-base">Collections</label>
    <input type="text" class="block w-full border border-gray-500 px-3 py-2 mt-2 mb-8 rounded-md text-sm md:text-md lg:text-base" id="collections">
    <div class="flex justify-between">
      <label for="tags" class="text-sm md:text-md lg:text-base">Tags</label>
      <a href="#" class="text-blue-500 text-sm md:text-md lg:text-base">Manage</a>
    </div>
    <input type="text" placeholder="Find or create tags" class="block w-full border border-gray-500 px-3 py-2 mt-2 mb-3 rounded-md text-sm md:text-md lg:text-base" id="tags">
  </div>
</template>