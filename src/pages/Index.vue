<template>
  <Layout>
    <section class="hero-container flex f-jac">
      <div class="hero-content text-center">
        <h1 class="mb-m">Pelipojat</h1>
        <h2 class="text-m">Pelistudio harrastuksena</h2>
      </div>
    </section>
    <section>
      <div class="text-content">
        <h1 class="mb-l">The boys</h1>
        <div class="flex f-wrap">
          <s-card
            v-for="crewmember in crew"
            :key="crewmember.id"
            :title="crewmember.name"
            :subtext="crewmember.tasks"
          />
        </div>
      </div>
    </section>
    <section>
      <div class="text-content">
        <h1>The Games</h1>
        <div class="mv-xl" v-for="(game, index) in games" :key="index">
          <h1 class="text-l mb-s">{{ game.title }}</h1>
          <p class="mv-xs">{{ game.description }}</p>
          <g-link :to="game.slug">Lue lisää > </g-link>
        </div>
      </div>
    </section>
  </Layout>
</template>

<script>
import Card from '@/components/Card'
export default {
  metaInfo: {
    title: 'Index',
  },
  components: {
    's-card': Card,
  },
  data() {
    return {
      crew: [
        {
          id: 1,
          name: 'Miika Savela',
          tasks: ['gamedev', 'suunnittelu', 'kahvin juominen', 'testaus'],
        },
        {
          id: 2,
          name: 'Tuomas Kajander',
          tasks: ['ideointi', 'tutkimus', 'testaus'],
        },
        {
          id: 3,
          name: 'Joni Grönthal',
          tasks: ['testaus', 'tutkimus', 'miikan hillitseminen'],
        },
        {
          id: 4,
          name: 'Anssi Ronkainen',
          tasks: ['ideointi', 'suunnittelu', 'huumori', 'tutkimusmetodologia'],
        },
        {
          id: 5,
          name: 'Santtu Heleä',
          tasks: ['kikkailu', 'testaus', 'webdev'],
        },
        {
          id: 6,
          name: 'Kalle Paakkunainen',
          tasks: ['farmaaminen', 'testaus', 'ideointi'],
        },
      ],
      games: [
        {
          title: 'Prototype 1',
          description: 'Lyhyt ja simppeli kuvaus prototyypistä',
          slug: 'proto-1',
        },
        {
          title: 'Prototype 2',
          description: 'Lyhyt ja simppeli kuvaus prototyypistä',
          slug: 'proto-2',
        },
        {
          title: 'Prototype 3',
          description: 'Lyhyt ja simppeli kuvaus prototyypistä',
          slug: 'proto-3',
        },
      ],
    }
  },
}
</script>

<style>
.hero-container {
  height: 90vh;
  flex-direction: column;
}
</style>
