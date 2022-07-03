<template>
  <div class="simple-slider">
    <div class="swiper-container">
      <div class="swiper-button-prev"></div>
      <div class="swiper-wrapper">
        <div
          class="swiper-slide"
          style="center center / cover no-repeat;height: 727px;">
        
        <button id="b1"  v-if="poke >= 1" @click="PokeMENOS" type="button" class="btn btn-primary ms-md-2">←</button>
        <button id="b1"  v-else type="button" class="btn btn-primary ms-md-2">←</button>
         <button id="b2"  @click="PokeMais" type="button" class="btn btn-primary ms-md-2">→</button>
          <div class="Modal">
           
            <!-- <div v-if="poke >= 1" @click="PokeMENOS" class="anterior"></div> -->
            <!-- <div v-else class="anterior"></div> -->
            <div class="divimg">
              <img class="img" :src="img" />
            </div>
            <div class="info">
              <h3 class="name">{{ name }}</h3>
              <div class="">
                <ul class="info">
                  <li
                    class="li1"
                    v-for="habi in habilidade"
                    :key="habi.ability.name"
                  >
                    Habilidade: {{ habi.ability.name }}
                  </li>
                  <li class="li2">base_experience: {{ base_experience }}</li>
                </ul>
              </div>
            
            </div>
                 <!-- <button type="button" class="btn btn-light">NEXT</button> -->
           
            <!-- <div @click="PokeMais" class="proximo"></div> -->
          </div>
        </div>
      </div>

      <div class="swiper-button-next"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal_vue",
  data() {
    return {
      data: {},
      // array_poke: [],
      url: "",
      poke_url: {},
      habilidade: {},
      habilidades: 0,
      img: "",
      base_experience: 0,
      poke: 1,
      name: "",
    };
  },
  methods: {
    openModal() {
      fetch("https://pokeapi.co/api/v2/pokemon/")
        .then((response) => response.json())
        .then((response) => {
          this.data = response.results[1];
          this.url = response.results[1].url;
          console.log(this.url);
          // console.log(response.results);
        });
    },
    get() {
      fetch('"' + this.url + '"')
        .then((response) => response.json())
        .then((response) => {
          this.poke_url = response;
          console.log('"' + this.url + '"');
          console.log(response);
          console.log('"' + this.url + '"');
          console.log(this.poke_url);
        });
    },
    PokeMENOS() {
      this.poke = this.poke - 1;
      fetch(`https://pokeapi.co/api/v2/pokemon/${this.poke}/`)
        .then((response) => response.json())
        .then((response) => {
          this.habilidade = response.abilities;
          this.img = response.sprites.front_default;
          this.base_experience = response.base_experience;
          this.name = response.name;
          console.log(response);
          console.log(response.sprites.front_default);
          // console.log(response.results);
        });
    },
    PokeMais() {
      this.poke = this.poke + 1;
      fetch(`https://pokeapi.co/api/v2/pokemon/${this.poke}/`)
        .then((response) => response.json())
        .then((response) => {
          this.habilidade = response.abilities;
          this.img = response.sprites.front_default;
          this.base_experience = response.base_experience;
          this.name = response.name;
          console.log(response);
          console.log(response.sprites.front_default);
          // console.log(response.results);
        });
    },
    PokeInit() {
      this.poke = this.poke + 1;
      fetch(`https://pokeapi.co/api/v2/pokemon/${this.poke}/`)
        .then((response) => response.json())
        .then((response) => {
          this.habilidade = response.abilities;
          this.img = response.sprites.front_default;
          this.base_experience = response.base_experience;
          this.name = response.name;
          console.log(response);
          console.log(response.sprites.front_default);
          // console.log(response.results);
        });
    },
  },
  watch: {
    //   poke(){
    //     fetch(`https://pokeapi.co/api/v2/pokemon/${this.poke}/`).then(response => response.json()).then(response => {
    //             this.habilidade = response.abilities;
    //             this.img = response.sprites.front_default;
    //             this.base_experience = response.base_experience;
    //             console.log(response);
    //             console.log(response.sprites.front_default);
    //         // console.log(response.results);
    //     });
  },
  created() {
    // console.log('Modal_ created');
    this.openModal();
    this.PokeInit();
    // this.get();
    // console.log(this.data);
  },
  beforeCreate() {
    // console.log('Modal_ beforeCreate');
  },
  mounted() {
    // console.log(this.data);
    // console.log('Modal_ mounted');
  },
};
</script>

<style>
#b1{
     margin-top:100px ;
     margin-left: 10px;
}
#b2 {
  margin-top:100px ;
  margin-right: 10px;
  float: right;
  /* width: 100px; */
}
.Modal {
  display: flex;
  align-content: center;
  justify-content: center;
  margin-top: 100px;
  margin-left: -20px ;
}
</style>