<template>
  <header class="bg-black text-white p-5 lg:px-12 flex justify-between items-center">
    <p class="font-semibold">Unsaved Product</p>
    <ul class="flex gap-4 items-center">
      <li class="hidden md:block"><button class="border border-white hover:border-red-400 ease-in-out duration-300 hover:text-red-400 rounded-md py-2 px-5">Discard</button></li>
      <li class="hidden md:block"><button class="bg-green-800 hover:bg-green-600 ease-in-out duration-300 rounded-md py-2 px-5">Save</button></li>
      <li class="md:hidden"><button class="border border-white hover:border-red-400 ease-in-out duration-300 hover:text-red-400 rounded-md py-2 px-3"><img src="../assets/icon/discard.svg" alt="d"/></button></li>
      <li class="md:hidden"><button class="bg-green-800 hover:bg-green-600 ease-in-out duration-300 rounded-md py-2 px-3"><img src="../assets/icon/save.svg" alt="s"/></button></li>
    </ul>
  </header>
</template>