<template>
  <div class="col-span-6 lg:col-span-4 lg:mr-4 bg-white rounded-md p-5 mt-12 shadow-md">
    <h3 class="font-semibold text-xl mb-6">Inventory</h3>

    <!-- Quantity -->
    <div class="flex items-center">
      <input
        type="checkbox"
        v-model="checked"
        @click="hidecont"
        class="w-5 h-5 text-base mr-2 rounded checked:bg-blue-500 after:text-xs after:font-awesome relative float-left cursor-pointer appearance-none border border-solid border-slate-150 bg-white bg-contain bg-center bg-no-repeat align-top after:absolute after:flex after:h-full after:w-full after:items-center after:justify-center after:text-white after:opacity-0 checked:border-0 checked:after:opacity-100"
      /><label class="text-sm md:text-md lg:text-base">Track quantity</label>
    </div>
    <div class="flex items-center justify-between py-5" v-if="!checked">
      <p class="font-semibold text-xs md:text-md lg:text-base">Quantity</p>
      <p class="text-gray-500 text-xs md:text-md lg:text-base">Not<br />tracked</p>
    </div>
    <div class="flex flex-col py-5 border-t my-3" v-if="checked">
      <div class="flex items-center justify-between py-4">
        <p class="font-semibold text-xs md:text-md lg:text-base">Quantity</p>
        <input type="number" min="0" value="1" class="border w-20 md:w-28 text-xs md:text-md lg:text-base pr-2 pl-4 py-2 rounded-md" />
      </div>
      <div class="flex items-center justify-between py-4">
        <p class="font-semibold text-xs md:text-md lg:text-base">Low Quantity Warning</p>
        <input type="number" min="0" value="1" class="border w-20 md:w-28 text-xs md:text-md lg:text-base pr-2 pl-4 py-2 rounded-md" />
      </div>
    </div>

    <!-- SKU / Barcode -->
    <div class="flex items-center border-t pt-6 pb-3">
      <input
        type="checkbox"
        v-model="checkedd"
        @click="hidecontt"
        class="w-5 h-5 text-base mr-2 rounded checked:bg-blue-500 after:text-xs after:font-awesome relative float-left cursor-pointer appearance-none border border-solid border-slate-150 bg-white bg-contain bg-center bg-no-repeat align-top after:absolute after:flex after:h-full after:w-full after:items-center after:justify-center after:text-white after:opacity-0 checked:border-0 checked:after:opacity-100"
      /><label class="text-sm md:text-md lg:text-base">This product has a SKU or barcode</label>
    </div>
    <div class="md:flex justify-between py-5" v-if="checkedd">
      <div class="flex flex-col w-full md:pr-12 mt-4 md:mt-0">
        <label class="mb-3 text-sm md:text-md lg:text-base" for="sku">SKU (Stock Keeping Unit)</label>
        <input type="text" id="sku" class="border border-gray-400 w-full p-2 rounded-md" />
      </div>
      <div class="flex flex-col w-full md:pl-12 mt-8 md:mt-0">
        <label class="mb-3 text-sm md:text-md lg:text-base" for="barcode">Barcode (ISBN, UPC, GTIN, etc.)</label>
        <input type="text" id="barcode" class="border border-gray-400 w-full p-2 rounded-md" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      checked: false,
      checkedd: false,
    };
  },
  methods: {
    hidecont() {
      this.checked = !this.checked;
    },
    hidecontt() {
      this.checkedd = !this.checkedd;
    },
  },
};
</script>
