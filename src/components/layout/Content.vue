<template>
  <div class="col-span-6 lg:col-span-4 flex flex-warp flex-col bg-white rounded-md p-5 lg:mr-4 shadow-md h-fit">
    <form action="">
      <label for="title" class="text-sm md:text-md lg:text-base">Title</label>
      <input
        type="text"
        placeholder="Short sleeve t-shirt"
        class="block w-full border border-gray-500 px-3 py-2 mt-2 mb-5 rounded-md text-sm md:text-md lg:text-base"
        id="title"
      />
      <label for="description" class="text-sm md:text-md lg:text-base">Description</label>
      <QuillEditor :options="options" id="description" />
    </form>
  </div>
</template>

<script>
import { QuillEditor } from "@vueup/vue-quill";
import "@vueup/vue-quill/dist/vue-quill.snow.css";

const toolbarOptions = [
  [{ header: [1, 2, 3, 4, 5, 6, false] }],
  ["bold", "italic", "underline", "strike"],
  [{ align: [] }, "blockquote", { list: "ordered" }, { list: "bullet" }],
  ["image", "video", "code-block"],
];

export default {
  components: {
    QuillEditor,
  },
  data() {
    return {
      options: {
        debug: "info",
        modules: {
          toolbar: toolbarOptions,
        },
        theme: "snow",
        placeholder: "",
      },
    };
  },
};
</script>
