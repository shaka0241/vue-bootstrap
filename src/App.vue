<template>
  <div id="app">
    <HelloWorld></HelloWorld>
    <b-jumbotron header="Informacion Basica" lead="Conexion api">
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
    </b-jumbotron>
    <b-jumbotron header="Informacion 5 dias" lead="Conexion api">
        <b-container class="bv-example-row">
          <b-row>
            <b-col>
              <ul v-for="santiago in santiagoscincos" v-bind:key="santiagoscincos.id">
                <li>{{santiago}}</li>
              </ul>
              <button @click="fetchSantiagocinco">Informacion 5 dias Santiago</button>
            </b-col>
            <b-col>
              <ul v-for="tokyo in tokyoscincos" v-bind:key="tokyoscincos.id">
                <li>{{tokyo}}</li>
              </ul>
              <button @click="fetchTokyocinco">Informacion 5 dias Tokyo</button>
            </b-col>
            <b-col>
              <ul v-for="paris in parisscincos" v-bind:key="parisscincos.id">
                <li>{{paris}}</li>
              </ul>
              <button @click="fetchPariscinco">Informacion 5 dias PAris</button>
            </b-col>
          </b-row>
        </b-container>
    </b-jumbotron>
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
      tokyos:[],
      santiagoscincos: [],
      parisscincos: [],
      tokyoscincos: []

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
        this.pariss = result.data
      })
    },
    fetchTokyo: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/1day/226396?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.tokyos = result.data
      })
    },
    fetchSantiagocinco: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/5day/60449?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.santiagoscincos = result.data
      })
    },
    fetchPariscinco: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/5day/133785?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.parisscincos = result.data
      })
    },
    fetchTokyocinco: function () {
      const baseURI = 'http://dataservice.accuweather.com/forecasts/v1/daily/5day/226396?apikey=SPDhK9W0OG4AGinAcZGn9t5gRqxg7cnA&language=es-cl'
      this.$http.get(baseURI)
      .then((result) => {
        this.tokyoscincos = result.data
      })
    },
  }
}
</script>

<style>

</style>
