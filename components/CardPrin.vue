<template>
  <div class="flex">
    <ul>
      <li v-for="player in players" :key="player.id" class="">
        <div>
          <h1>{{ player.firstName }} {{ player.lastName }}</h1>
        </div>
        <div> <p>{{ player.status }}</p></div>
      </li>
    </ul>
  </div>
</template>

<script>
import { TOP_CIRCLE } from '~/constants/api.js'

export default {
  name: 'CardPrin',
  data () {
    return {
      players: [],
      lasd: null
    }
  },
  mounted () {
    this.$axios.get(TOP_CIRCLE).then((response) => {
      this.players = response.data
    })
    this.lasd = TOP_CIRCLE
  }
}
</script>
