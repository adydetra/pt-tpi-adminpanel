<script setup>
  import Content from '../components/layout/Content.vue'
  import Sidebar from '../components/layout/Sidebar.vue'
  import Inventory from '../components/layout/Inventory.vue'
</script>

<template>
  <section class="grid grid-cols-6 px-5 py-12 lg:px-12 min-h-screen">
    <Content />
    <Sidebar />
    <Inventory />
    <section class="col-span-6 lg:col-span-4 flex justify-center lg:justify-end lg:mr-4">
      <button class="bg-green-600 hover:bg-green-500 ease-in-out duration-300 rounded-md text-white py-2 mt-14 px-5">Save</button>
    </section>
  </section>
</template>

<style>
  .ql-toolbar.ql-snow {
    margin: 0.5rem 0 0 0 !important;
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
  }
  .ql-editor {
    height: 13rem;
  }
  .ql-container {
    border-bottom-right-radius: 5px;
    border-bottom-left-radius: 5px;
  }
</style>