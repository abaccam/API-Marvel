<template>
  <section>
    <div id="lignes" class="container-row">
      <div id="image" 
      v-bind:style="{ backgroundImage: 
      'url(' + character.thumbnail.path + '.' + character.thumbnail.extension + ')' }">
      </div>
      <div id="nom">
        <h1 @click="characterData=true">{{character.name}}</h1>
      </div>
    </div>

    <div class="modal-body" v-if="characterData" id="modal">
      <div class="container-fluid">
        <div class="row">
          <div id="characPic" class="col-md-6" v-bind:style="{ backgroundImage: 'url(' + character.thumbnail.path + '.' + character.thumbnail.extension + ')' }"></div>
          <div id="modalName" class="col-md-6 ml-auto">{{character.name}}</div>
        </div>
        <div class="row">
          <div class="col-md-12 sl-auto">{{character.description}} Comics:{{character.comics.available}}</div>
        </div>
        <div class="row">
         <div class="col-md-12 ml-auto" 
              v-for="comic in character.comics.items.slice(0, 3)" :key="comic.name">{{comic.name}}</div>
        </div>
        <div class="col-md-6 ml-auto"></div>
        <div class="modal-footer">
          <button @click="characterData=false" type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        </div>      
      </div>
    </div>
  </section>
  
</template>

<script>
export default {
  name : "Character",
  props: {
    character: {
      type: Object,
    }
  },
  data() {
    return {
      characterData: false
    }
  }
}
</script>

<style>
.container-row {
  display : flex;
  flex-direction: row;
  justify-content: center;
}

.container-col {
  display : flex;
  flex-direction: column;
  justify-content: space-between;
}

#lignes{
  justify-content: flex-start;
  border: 3px solid rgb(255, 255, 255);
  width:500px;
  height:80px; 
}

#lignes:hover{
    border: 4px solid #e92227;

}

#image {
  border: 3px solid black;
  width: 145px;
  background-size: cover;

}

#nom {
  /* border: 1px solid white; */
  width: 420px;
}

h1{
  font-size: 25px;
  text-align: center;
  color:white;
}

h1:hover{
  font-size: 25px;
  text-align: center;
  color:#e92227;
}

#modalName{
  font-size: 25px;
  text-align: center;
  color:black;
}

#modal{
  background-color: white;
}

#characPic{
  width: 200px;
  height: 150px;
  background-size: cover;
  border:1px solid grey;

}

</style>
