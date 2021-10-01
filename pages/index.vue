<template>
  <!-- moldura -->
  <div class="space-y-2 md:flex md:space-x-4 md:space-y-0 p-6">
    <!-- perfil pessoal -->
    <div class="div border-2 rounded-md space-y-4 md:flex-grow p-4">
      <!-- foto e nome  -->
      <div class="div flex flex-wrap items-center gap-4 md:flex-col">
        <img class="w-16 h-16 rounded-full flex-shrink-0 border-2 border-green-500 p-1 md:w-32 md:h-32" src="https://images.unsplash.com/photo-1633010999952-dd67157f7b81?ixid=MnwxMjA3fDB8MHxleHBsb3JlLWZlZWR8MTd8fHxlbnwwfHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="">
        <div class="flex flex-col">
          <span class="text-xl font-bold">Nome kjaksjakjsd</span>
          <span class="text-sm font">asdasdasd</span>
        </div>
      </div>
      <p class="text-grey-500 border-t border-solid" />
      <!-- bio e info-->
      <div class="space-y-4">
        <p class="text-md">Adsdfsd sdfsd sdfsf sdfs sdc erfw wkolf weflkv wefkw</p>
        <!-- adress, phone ,email...-->
        <div class="flex-col text-sm space-y-1">
          <div class="flex space-x-4 items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
            <p>São Paulo, Brasil</p>
          </div>
          <div class="flex space-x-4 items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
            <p>aquiles.cout@gmail.com</p>
          </div>
          <div class="flex space-x-4 items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
            <p>+55 11 98290-7503</p>
          </div>
        </div>
      </div>
    </div>
    <!-- conteudo do curriculo -->
    <div class="justify-center items-center space-y-4 border-2 rounded-md p-4 md:flex-grow md:w-4/5">
      <!-- cards de habilidades -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 xl:grid-cols-4 gap-4 border-2">
        <div class="border-2">
          1
        </div>
        <div class="border-2">
          2
        </div>
        <div class="border-2">
          3
        </div>
        <div class="border-2">
          4
        </div>
        <div class="border-2">
          5
        </div>
        <div class="border-2">
          6
        </div>
        <div class="border-2">
          7
        </div>
      </div>
      <div class="text-xl font-bold">
        <h1 class="flex justify-center">
          Xp
        </h1>
      </div>
      <!-- card de experiencias -->

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-4">
        <CardExperiencia v-for="xp in experiencias" :key="xp.empresa">
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
        </CardExperiencia>
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
