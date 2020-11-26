<template>
  <div>
    <div class="card text-center m-2">
      <div class="card-header">
        <img class="img_pokedex" src="../assets/pokemon.png" alt="">
      </div>

      <div class="card-body">
        <div class="form-1 container-fluid" >
          <div class="row">
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-4" id="pokemon-1"></div>
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-4" id="chartContainer"></div>
            <div class="pantalla col-12 col-sm-12 col-md-4 col-lg-4 col-xl-4" id="pokemon-2">
               <ul></ul>
            </div>
          </div>
        </div>

        <div class="form-group mx-sm-5 m-3 ">
          <label class="sr-only"></label>
          <input class="form-control form-2 text-center"  placeholder="Ingresa el n° o el nombre de tu Pokemon">
          <a href="#" class="btn btn-dark p-4 " id="buscar">Buscar</a>
        </div>
      </div>

        <div class="card-footer text-muted">
        </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PokeGuia',
  props: {
  }
}
</script>

<style scoped>
body {
    margin: 0;
    padding: 0;
    border: 0;
    font-family: 'Goldman', cursive;   
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
    box-shadow: 1px 1px 3px 4px  #965858;    
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
h4 {
    background-color: yellow;
    border-radius: 15px;
    text-align: center;
    font-size: 15px;
    margin: 10px;
    padding: 10px;
}
ul {
    padding: 0;
}
li {
    padding-top: 5px;
    text-align: center;
}
p {
    padding-top: 5px;
    text-align: center;
}

.img_pokemon {
    width: 200px;
    align-content: center;
}
#chartContainer {
    height: 300px;
    width: 100%;
    padding: 0;
}
.btn {
    box-shadow: 1px 1px 3px 4px  #965858;  
    border-radius: 25px;
    margin-top: 60px;
}
</style>
