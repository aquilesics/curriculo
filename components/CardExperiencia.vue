<template>
  <div class="shadow rounded-lg p-4 divide-y divide-blue-400">
    <div class="pb-2">
      <h3 class="font-bold text-md">
        <slot name="empresa" />
      </h3>
      <div class="flex flex-nowrap justify-between">
        <h1 class="">
          <slot name="cargo" />
        </h1>
        <h1 class="ml-6 text-xs">
          <slot name="periodo" />
        </h1>
      </div>
    </div>
    <h1 class="pt-4 text-sm space-y-1">
      <slot name="descricao" />
    </h1>
  </div>
</template>

<script>
export default {}
</script>
