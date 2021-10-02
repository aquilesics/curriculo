<template>
  <div class="bg-gray-100 place-self-auto cursor-pointer bg-white shadow-md rounded-md p-4 transition duration-500 ease-in-out hover:bg-purple-300 transform hover:-translate-y-1 hover:scale-105" @click="show= !show">
    <div class="flex justify-center  h-10">
      <slot name="image" />
    </div>
    <p v-if="show" class="mt-2  border-purple-300 border-t border-solid" />
    <h1 v-if="show" class="flex text-sm md:text-md font-bold justify-center m-1">
      <slot name="title" />
    </h1>
    <h1 v-if="show" class=" text-xs space-y-1 justify-center">
      <slot name="lista" />
    </h1>
  </div>
</template>

<script>

export default {
  data () {
    return { show: false }
  }
}
</script>
