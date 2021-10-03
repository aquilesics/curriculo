<template>
  <!-- moldura -->
  <div class="space-y-2 md:flex min-h-screen md:space-x-4 md:space-y-0 p-4 md:p-6 lg:p-8 bg-gray-100">
    <!-- perfil pessoal -->
    <div class="div border-2 rounded-md space-y-4 md:flex-grow p-4">
      <!-- foto e nome  -->
      <div class="div flex flex-wrap items-center gap-4 md:flex-col">
        <img class="w-16 h-16 rounded-full flex-shrink-0 border-2 border-purple-300 p-1 md:w-32 md:h-32" src="../assets/1_me_greyscale.jpg" alt="">
        <div class="flex flex-col">
          <span class="text-xl font-bold">Aquiles Coutinho</span>
          <span class="text-sm font">@aqls_art</span>
        </div>
      </div>
      <p class="text-grey-500 border-t border-solid" />
      <!-- bio e info-->
      <div class="space-y-4">
        <p class="text-md">
          Gosto de automatizar tarefas chatas e adoro arte!
        </p>
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
          <div class="flex space-x-4 items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              aria-hidden="true"
              viewBox="0 0 16 16"
              version="1.1"
              data-view-component="true"
              class="w-4 h-4"
            >
              <path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z" />
            </svg>
            <a href="https://github.com/aquilesics" target="_blank" rel="noopener noreferrer">
              aquilesics
            </a>
          </div>
        </div>
      </div>
    </div>
    <!-- conteudo do curriculo -->
    <div class="justify-center items-center space-y-4 border-2 rounded-md p-4 md:flex-grow md:w-4/5">
      <p class="flex-col text-center items-center justify-center">
        Precisando de uma mãozinha? 👋 <br>
        Talvez eu possa te ajudar:
      </p>
      <!-- cards de habilidades -->
      <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-4 items-center jsutify-center">
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
      <div class="text-xl font-bold">
        <p class="text-gray-900 border-t border-solid" />
        <h1 class="flex justify-center mt-4">
          Experiências:
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
        { title: 'Flask (Intermediário)', items: ['REST api', 'Blueprints', 'SPA'], image: 'flask.svg' },
        { title: 'Python (Intermediário)', items: ['Lambda, map, filter', 'Funções geradoras (yield)', 'Functools (Lru_cache, reduce, singledispatch)', 'ABC', 'Virtual env', 'Packing e unpacking'], image: 'python.svg' },
        { title: 'Bash (Intermediário)', items: ['Cat, ls, cd e outros programas GNU', 'AWK pra processar texto', 'STDIN e STDOUT'], image: 'bash.svg' },
        { title: 'Pandas (básico)', items: ['ETL de dataframes', 'jupyter notebook', 'loc, iloc e outros métodos comuns'], image: 'pandas.svg' },
        { title: 'Docker', items: ['Simular ambientes de Prod'], image: 'docker.svg' },
        { title: 'Git', items: ['Commits, pushs, brench'], image: 'git.svg' },
        { title: 'Java Script (básico)', items: ['Node', 'Noções de Funções e objetos'], image: 'js.svg' },
        { title: 'css', items: ['Responsive Design, Flex, Grid', 'Animations etc'], image: 'css.svg' },
        { title: 'vue (básico)', items: ['Single components', 'Templates, diretivas, props'], image: 'vue.svg' },
        { title: 'Mongo DB', items: ['Banco de dados não relacional'], image: 'mongodb.svg' },
        { title: 'Power bi (Intermediário)', items: ['Dax e Formula M', 'Integração com Views'], image: 'powerbi.svg' },
        { title: 'Postgresql (básico)', items: ['DML, Views', 'Groups, joins e relações', 'Funções personalizadas'], image: 'postgres.svg' }
      ],
      experiencias: [
        {
          empresa: 'Accenture',
          cargo: 'Analista Financeiro Junior',
          periodo: {
            inicio: 'Set/2019',
            fim: 'Set/2020'
          },
          descricao: ['Manipulação de Dados e Reports Diários/Semanais.', 'Automação de Processos (Power Automate).', 'Fluxo de emails e respostas automáticas.', 'Substituição de reports em excel para dashboards.', 'Downloads automáticos utilizando Powershell ou Python (Requests ou Scrapy).']
        },
        {
          empresa: 'Quickfast',
          cargo: 'Analista de Suporte',
          periodo: {
            inicio: 'Fev/2018',
            fim: 'Dez/2018'
          },
          descricao: ['Analista do banco de dados local (Firebird).', 'Relator de bugs da aplicação mobile.', 'Auxiliar Clientes na utilização do sistema ERP.']
        },
        {
          empresa: 'DIGI',
          cargo: 'Freelancer Power Bi',
          periodo: {
            inicio: 'Jul/2021',
            fim: 'Jul/2021'
          },
          descricao: ['DML/DDL com postgres e mysql.', 'Criação de dashboards utilizando Powerbi.', 'DAX, Power Query e Language M.']
        }
      ]
    }
  }
}

</script>
