<script setup>
  import vSelect from 'vue-select'
  import "vue-select/dist/vue-select.css";

  import { ref } from 'vue'
  import {
    TransitionRoot,
    TransitionChild,
    Dialog,
    DialogPanel,
    DialogTitle,
  } from '@headlessui/vue'
  
  const isOpen = ref(false)
  
  function closeModal() {
    isOpen.value = false
  }
  function openModal() {
    isOpen.value = true
  }
</script>

<template>
  <v-select :options="product" v-model="product_select" class="text-sm md:text-md lg:text-base text-gray-400 block w-full border border-gray-500 px-1 py-1 mt-2 mb-8 rounded-md" placeholder="Search product categories">
    <template #list-footer>
      <li class="px-2 lg:px-5 pb-3 mb-3"><button type="button" @click="openModal" class="text-blue-400 text-xs md:text-md lg:text-base">Add Another Category</button></li>
    </template>
  </v-select>

  <!-- Modal -->
  <TransitionRoot appear :show="isOpen" as="template">
    <Dialog as="div" @close="closeModal" class="relative z-10">
      <TransitionChild
      as="template"
      enter="duration-300 ease-out"
      enter-from="opacity-0"
      enter-to="opacity-100"
      leave="duration-200 ease-in"
      leave-from="opacity-100"
      leave-to="opacity-0"
      >
      <div class="fixed inset-0 bg-black bg-opacity-25" />
      </TransitionChild>
  
      <div class="fixed inset-0 overflow-y-auto">
      <div class="flex min-h-full items-center justify-center p-4 text-center">
        <TransitionChild
        as="template"
        enter="duration-300 ease-out"
        enter-from="opacity-0 scale-95"
        enter-to="opacity-100 scale-100"
        leave="duration-200 ease-in"
        leave-from="opacity-100 scale-100"
        leave-to="opacity-0 scale-95"
        >
        <DialogPanel class="w-full max-w-2xl transform overflow-hidden rounded-2xl bg-white p-6 text-left align-middle shadow-xl transition-all">
          <DialogTitle as="h3" class="text-lg font-bold leading-6 text-gray-900 mb-6 lg:mb-8">Add Category</DialogTitle>
          <div class="mt-2 px-3 lg:px-5">
            <form action="">
              <label for="category-name" class="text-red-500 text-sm md:text-md lg:text-base">Category Name*</label>
              <input type="text" placeholder="Example: Category A" class="text-sm md:text-md lg:text-base block w-full border border-gray-500 px-3 py-2 mt-2 mb-8 rounded-md" id="category-name" required oninvalid="this.setCustomValidity('“category nama” tidak boleh kosong.')"/>
              <label for="parent-category" class="text-sm md:text-md lg:text-base">Parent Category</label>
              <input type="text" placeholder="Example: Category A" class="text-sm md:text-md lg:text-base block w-full border border-gray-500 px-3 py-2 mt-2 mb-8 rounded-md" id="parent-category"/>
              
              <label class="text-sm md:text-md lg:text-base">Category Banner (200 x 200)</label>
              <div class="w-full mt-3 mb-6 h-40 flex flex-col justify-center items-center border-2 border-gray-300 rounded-lg border-dashed">
                <div class="flex gap-3 lg:gap-6 items-center">
                  <input type="file" id="file-banner" class="hidden"/>
                  <label for="file-banner" class="cursor-pointer text-blue-600 bg-blue-100 py-1 px-3 rounded-md text-xs md:text-md lg:text-base">Add Files</label>
                  <input type="file" id="url-banner" class="hidden"/>
                  <label for="url-banner" class="cursor-pointer text-blue-500 border-b border-blue-300 text-xs md:text-md lg:text-base">Add from URL</label>
                </div>
                <label class="block text-gray-500 mt-2 text-xs md:text-md lg:text-base">Accepts images, videos, or 3D models</label>
              </div>

              <label class="text-sm md:text-md lg:text-base">Category Icon (200 x 200)</label>
              <div class="w-full mt-3 h-40 flex flex-col justify-center items-center border-2 border-gray-300 rounded-lg border-dashed">
                <div class="flex gap-3 lg:gap-6 items-center">
                  <input type="file" id="file-icon" class="hidden"/>
                  <label for="file-icon" class="cursor-pointer text-blue-600 bg-blue-100 py-1 px-3 rounded-md text-xs md:text-md lg:text-base">Add Files</label>
                  <input type="file" id="url-icon" class="hidden"/>
                  <label for="url-icon" class="cursor-pointer text-blue-500 border-b border-blue-300 text-xs md:text-md lg:text-base">Add from URL</label>
                </div>
                <label class="block text-gray-500 mt-2 text-xs md:text-md lg:text-base">Accepts images, videos, or 3D models</label>
              </div>

              <div class="mt-8 flex justify-end gap-4">
                <button type="button" class="border border-gray-400 hover:border-red-400 hover:text-red-400 rounded-md py-2 px-5" @click="closeModal">
                  Cancel
                </button>
                <button type="save" class="bg-green-800 hover:bg-green-600 text-white rounded-md py-2 px-5">
                  Save
                </button>
              </div>
            </form>
          </div>
        </DialogPanel>
        </TransitionChild>
      </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>

<script>
export default {
  data() {
    return {
      product: ["Category A", "Category B", "Category C", "Category D"],
      names: [],
      product_select: '',
      id: ''
    };
  },
};
</script>

<style>  
  .vs__search::placeholder,
  .vs__dropdown-toggle {
    border: none;
  }
  .vs__dropdown-menu {
    border: 1px solid #AAA;
    border-radius: 5px;
    padding: 0 1rem;
  }
  .vs__dropdown-option {
    padding: 0.6rem 1rem;
    margin: 1rem 0;
    border-radius: 5px;
  }
  @media (max-width: 1024px) {
    .vs__search, .vs__dropdown-option {
    font-size: 14px !important;
    }
    .vs__dropdown-option {
      padding: 0.6rem 0.4rem;
    }
  }
</style>