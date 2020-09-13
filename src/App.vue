<template>
  <div id="app" @touchmove.prevent>
    <v-header></v-header>
    <div class="tab-wrapper">
    </div>
  </div>
</template>

<script>
  import VHeader from 'components/v-header/v-header'
  import { getSeller } from './api'

  export default {
    name: 'App',
    data () {
      return {
        seller: {}
      }
    },
    created () {
      getSeller().then((seller) => {
        this.seller = seller
      })
    },
    components: {
      VHeader
    }
  }
</script>

<style lang="stylus" scoped>
  #app
    .tab-wrapper
      position: fixed
      top: 136px
      left: 0
      right: 0
      bottom: 0
</style>
