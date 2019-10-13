<template>
  <div id="app">
    <HelloWorld></HelloWorld>
    <b-container class="bv-example-row">
  <b-row>
    <b-col>
      <ul v-for="santiago in santiagos" v-bind:key="santiagos.id">
      <li>{{santiago}}</li>
      </ul>
      <button @click="fetchSantiago">Informacion Actual Santiago</button>
    </b-col>
    <b-col>
      <ul v-for="paris in pariss" v-bind:key="pariss.id">
      <li>{{paris}}</li>
      </ul>
      <button @click="fetchParis">Informacion Actual Paris</button>
    </b-col>
    <b-col>
      <ul v-for="tokyo in tokyos" v-bind:key="tokyos.id">
      <li>{{tokyo}}</li>
      </ul>
      <button @click="fetchTokyo">Informacion Actual tokyo</button>
    </b-col>
  </b-row>
</b-container>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
    data () {
    return {
      santiagos: [],
      pariss:[],
      tokyos:[]
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    fetchSantiago: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/1day/60449?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.santiagos = result.data
      })
    },
    fetchParis: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/1day/133785?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.santiagos = result.data
      })
    },
    fetchTokyo: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/1day/133785?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.santiagos = result.data
      })
    },
  }
}
</script>

<style>

</style>
