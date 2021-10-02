<!-- Please remove this file from your project -->
<template>
  <div class="flex bg-gray-500 p-12">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <div class="flex space-x-4 min-h-screen ">
      <div class="flex-grow space-y-4 w-1/4 bg-white overflow-hidden shadow sm:rounded-lg p-6">
        <img class="w-32 h-32 rounded-full mx-auto" src="@/assets/cover.jpg">
        <h2 class="justify-center text-xl leading-7 font-semibold">
          Name Lastname
        </h2>
        <p class="pt-4 text-gray-800 border-t border-dashed" />
        <p class="font-medium text-grey-500">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry.
          Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
          when an unknown printer took a galley of type and scrambled it to make a type
          specimen book. It has survived not only five centuries,
        </p>
      </div>
      <div class="flex-column w-3/4 justify-center items-center bg-white overflow-hidden shadow sm:rounded-lg p-6">
        <h2 class="text-xl leading-7 font-semibold text-center mb-4">
          Habilidades:
        </h2>
        <div class="flex flex-wrap justify-center">
          <CardHabilidade v-for="icon in icons" :key="icon.title">
            <img slot="image" :src="require(`@/assets/${icon.image}`)">
            {{ icon.image }}
            <h1 slot="title">
              {{ icon.title }}
            </h1>
            <li v-for="item in icon.items" :key="item.title" slot="lista">
              {{ item }}
            </li>
          </CardHabilidade>
        </div>
        <p class="mt-4 pt-4 text-gray-800 border-t border-dashed" />
        <h2 class="text-xl leading-7 font-semibold text-center mb-4">
          Experiências:
        </h2>
        <div class="flex flex-wrap">
          <experienciaCard v-for="xp in experiencias" :key="xp.empresa">
            <p slot="empresa">
              {{ xp.empresa }}
            </p>
            <p slot="cargo">
              {{ xp.cargo }}
            </p>
            <p slot="periodo">
              {{ xp.periodo.inicio + " - " + xp.periodo.fim }}
            </p>
            <li v-for="desc in xp.descricao" slot="descricao" :key="desc">
              {{ desc }}
            </li>
          </experienciaCard>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      icons: [
        { title: 'frutas', items: ['has been the industrys standard dummy text ever since the 1500s', 'uva'], image: 'powerbi.svg' },
        { title: 'carros', items: ['ford', 'when an unknown printer a type It has survived not only five centuries,', 'Ka'], image: 'python.svg' },
        { title: 'carros', items: ['ford', 'opel', 'Ka'], image: 'bash.svg' },
        { title: 'carros', items: ['ford', 'opel', 'Ka'], image: 'bash.svg' },
        { title: 'carros', items: ['ford', 'opel', 'Ka'], image: 'bash.svg' }
      ],
      experiencias: [
        {
          empresa: 'Accenture',
          cargo: 'Analista Junior',
          periodo: {
            inicio: 'ago/2020',
            fim: 'dez/2020'
          },
          descricao: ['fazia cafe', 'vendia pc positivo']
        },
        {
          empresa: 'casas bahia',
          cargo: 'vendedor',
          periodo: {
            inicio: 'set/2020',
            fim: 'dez/2020'
          },
          descricao: ['fazia cafe tbm', 'planfetagem']
        }
      ]
    }
  }
}
</script>
