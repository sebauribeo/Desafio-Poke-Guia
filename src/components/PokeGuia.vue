<template>
  <div>
    <div class="card text-center m-2">
      <div class="card-header">
        <img class="img_pokedex" src="../assets/pokemon.png" alt="">
      </div>
      <div class="card-body">
        <div class="form-1 container-fluid" >
          <div class="row">
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-4">
              <h2>Caracteristicas</h2>
              <h3>N° pokedex: {{poke.id}}</h3>
              <h3>Peso: {{poke.weight}}</h3>
              <h3>Altura: {{poke.height}} Ft</h3>
              <h3></h3>
            </div>
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-6">
              <h2>{{poke.name}}</h2>
              <img :src="getImage" alt="">
              <ul>
                <li class="types" v-for="(tipo, index) in poke.types" :key="index">{{tipo.type.name}}</li>
              </ul>
              </div>
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-4">
              <ul>
                <h2>Habilidades:</h2>
                 <li v-for="(pokemon, index) in poke.abilities" :key="index"><h3>{{pokemon.ability.name}}</h3></li>
              </ul>
            </div>
            
          </div>
        </div>
      </div>
      <form @submit.prevent="buscar">
        <div class="form-group mx-sm-5 m-3 ">
          <input v-model="pokeId" type="search" class="form-control form-2 text-center" placeholder="Ingresa el n° o el nombre de tu Pokemon" aria-label="Search" aria-describedby="button-addon2">
          <div>
           <button class="btn btn-dark p-4 text-center" type="submit">Buscar</button>
          </div>
        </div>
      </form>
    </div>
  </div>

</template>

<script>
export default {
  name: 'PokeGuia',
  data() {
    return {
      pokeId: '',
      poke: {},
    }
  },
  mounted() {
      fetch("https://pokeapi.co/api/v2/pokemon/pikachu")
      .then((resp) => resp.json())
      .then((result) => {
        this.poke = result;
      })
  },
  methods: {
    buscar(){
      fetch("https://pokeapi.co/api/v2/pokemon/"+this.pokeId)
      .then((resp) => resp.json())
      .then((result) =>{
        this.poke = result;
        this.pokeId = "";
      })
      .catch((error) => {
        console.log(error)
        alert("El nombre o número no es correcto");
      })
    }
  },

  computed:{
     getImage() {
       if (this.poke.sprites) {
         return this.poke.sprites.other['official-artwork'].front_default;
       }else {
         return '';
       }
     }
  },
  
}
</script>

<style scoped>
body {
    margin: 0;
    padding: 0;
    border: 0;
}

.card {
    background-color: #c00f0f;
    border-radius: 30px;
}
.img_pokedex {
    width: 300px;
    height: 80px;
}
.form-1 {
    width: 100%;
    height: auto;
    background-color: #9ae4ed;
    border: 10px solid #434343;
    border-radius: 10px;
    margin-bottom: 10px;
    box-shadow: 0 0 5px 5px  #965858;    
}
.pantalla {
    height: 100%;
    display: inline-block;
    font-size: 15px;
    color: black;
    align-content: center;
}
.pantalla img {
    width: 200px;
    height: 200px;
}
.types {
  display: inline;
  list-style: none;
  background: rgb(46, 46, 45);
  color: white;
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
}
h2 {
    background-color: yellow;
    border-radius: 15px;
    text-align: center;
    font-size: 25px;
    margin: 10px;
    padding: 10px;
    border: 4px solid black;
}
h3 {
  padding: 10px;
}
ul {
  padding: 0;
}
li {
    padding-top: 5px;
    margin-top: 30px;
    list-style: none;

}
p {
    padding-top: 5px;
    text-align: center;
}

.img_pokemon {
    width: 200px;
    align-content: center;
}

.btn {
    box-shadow: 1px 1px 3px 4px  #965858;  
    border-radius: 25px;
    margin-top: 60px;
    transition: 1s;
}

</style>
