<template>
  <div class="flex-grow w-40 max-w-xs bg-white shadow sm:rounded-lg m-2 p-4">
    <div class="flex justify-center h-10">
      <slot name="image" />
    </div>
    <p class="mt-2  text-gray-800 border-t border-dashed" />
    <h1 class="flex justify-center m-1">
      <slot name="title" />
    </h1>
    <h1 class=" text-xs space-y-1 justify-center    ">
      <slot name="lista" />
    </h1>
  </div>
</template>

<script>

export default {}
</script>
