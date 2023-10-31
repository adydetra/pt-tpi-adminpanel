<script setup>
import Modal from "../Modal.vue";
const input = "block w-full border border-gray-500 px-3 py-2 mt-2 rounded-md text-sm md:text-md lg:text-base";
const label = "text-sm md:text-md lg:text-base";
</script>

<template>
  <div class="col-span-6 lg:col-span-2 bg-white rounded-md p-5 lg:ml-4 mt-12 lg:mt-0 shadow-md h-fit">
    <h3 class="font-semibold text-xl mb-6 flex gap-2">Product Organization <img src="../../assets/icon/icon.svg" class="w-5 lg:w-6 -mt-2" alt="icon" /></h3>
    <label for="product-category" class="label">Product Category</label>
    <Modal />
    <label for="product-brand" class="label">Product Brand</label>
    <input type="text" placeholder="e.g., T-Shirt" class="mb-8" :class="input" id="product-brand" />
    <label for="collections" class="label">Collections</label>
    <input type="text" class="mb-8" :class="input" id="collections" />
    <div class="flex justify-between">
      <label for="tags" class="label">Tags</label>
      <a href="#" class="text-blue-500" :class="label">Manage</a>
    </div>
    <input type="text" placeholder="Find or create tags" class="mb-3" :class="input" id="tags" />
  </div>
</template>
