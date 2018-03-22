<template>
<section>
    <div class="container-row">
      <div id="liste" class="container-col" >
        <Character v-for="character in characters" :key="character.id" :character="character"/>
      </div>
    </div>
   
  </section>
</template>

<script>
import axios from 'axios'
import Character from '../components/Character'

export default {
  name: 'List',

  components: {
    Character
  },

  data() {
    return {
      characters:[]
    }
  },

  methods:{
    
      },

  beforeCreate() {
    axios.get(`https://gateway.marvel.com:443/v1/public/characters?limit=20&offset=100&ts=1&apikey=b067e96dad0fe12190e20585ac9c4c13&hash=f75b2bc54553cfc830d01b2b68cd30d5`)
      .then((response) => {this.characters = response.data.data.results;
              console.log(response.data.data.results)})
      // .catch( (error) => console.error(error));
  }
}
</script>

<style>
.container-row {
  display : flex;
  flex-direction: row;
  justify-content: center;

}

#liste{
  width: 500px;
  height: 1900px;
  margin-top: 50px;
}

 #nom {
  width: 420px;
  background-color: rgba(0, 0, 0, 0.8);
}
</style>
