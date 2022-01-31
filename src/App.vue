<template>
  <div id="app">
    <h1>Random Gift Cat</h1>
    <section class="red">
      <form >
        <div><label>Título:</label>
          <input type="text" class="form-control" v-model="titulo">
        </div>
        <div class="form-group">
          <label>Filtro:</label>
          <select class="form-control" v-model="filtro">
            <option value="blur">Blur</option>
            <option value="mono">Mono</option>
            <option value="negative">Negative</option>
            <option value="paint">Paint</option>
            <option value="pixel">Pixel</option>
            <option value="sepia">Sepia</option>
          </select>
        </div>
        <div>
          <label>Color:</label>
          <select class="form-control" v-model="color">
            <option value="pink">Rosado</option>
            <option value="aqua">Celeste</option>
            <option value="red">Rojo</option>
             <option value="orange">Naranjo</option>
            <option value="purple">Morado</option>
            <option value="YellowGreen">Verde</option>
          </select>
        </div>
        <div>
          <label>Tamaño:</label>
          <input type="text" class="form-control" v-model="tamano" @keyup.enter="showImage">
        </div>
      </form>
    </section>
    <button type="button" class="btn btn-success" @click="showImage">Obtener mi gatito</button>
    <section id="image">
      <div class="">
        <img :src="urlImage" alt="">
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'Random Gif Cat',
      urlImage: null,
      titulo: null,
      color: null,
      filtro: null,
      tamano: null
    }
  },
  methods: {
    showImage() {
      this.urlImage = `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}`;
      console.log('url', this.urlImage);
    }
  }
}
</script>

<style>

h1{
  color: rgb(60, 60, 60);
  
}

html {
  background-color: rgb(115, 176, 250);
  
}

#app {
  font-family: Courier, "Lucida Console", monospace;
  text-align: center;
  margin-top: 30px;
}


.red {
  background-color: #ff7ce0;
  width: 100%;
  height: 200px;
  margin-top: 50px;
  margin-bottom: 50px;
}

.image {
  height: 1000px;
}

.btn {
margin-bottom: 80px;
}

.form-control {
margin-top: 22px;
}

</style>