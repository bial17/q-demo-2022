<template>
  <q-page padding>
    <div class="q-pa-md row items-stretch">
      <plat-comp v-for="p in plats"
      :key="p.id"
      :passeplat="p"
       @supprimer="supprimerPlat"
        ></plat-comp>
      </div>
  </q-page>
</template>

<script>

import PlatComp from 'components/PlatComp'
export default {
  components: { PlatComp },
  data () {
    return {
      plats: [
        {
          id: 23,
          image: 'https://i.imgur.com/0umadnY.jpg',
          nom: 'Burger',
          description: 'Un hamburger est un sandwich composé d\'une ou plusieurs tranches de viande hachée, généralement du bœuf, placées dans un petit pain ou une brioche.',
          note: '4/5'
        },
        {
          id: 76,
          image: 'https://i.imgur.com/b9zDbyb.jpg',
          nom: 'Pizza',
          description: 'La pizza est un plat savoureux d\'origine italienne, consistant en une base généralement ronde et aplatie de pâte levée à base de blé.',
          note: '5/5'
        },
        {
          id: 85,
          image: 'https://i.imgur.com/RbKjUjB.jpg',
          nom: 'Petits choux',
          description: 'Le chou de Bruxelles est une variété de chou, plante herbacée de la famille des Brassicaceae. C’est vraiement pas bon...',
          note: '1/5'
        }

      ]
    }
  },
  methods: {
    supprimerPlat (idplat) {
      this.plats = this.plats.filter(function (plat) {
        return plat.id !== idplat
      })
    }
  }
}

</script>
