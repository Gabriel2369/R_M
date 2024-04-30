<script setup>
import ListCharacters from '@/components/ListCharacters.vue';
import { onMounted, reactive, ref } from 'vue';

let personagens = reactive(ref())



onMounted(() =>{
  fetch("https://rickandmortyapi.com/api/character?limit=auto&offset=0")
  .then(response => response.json())
  .then(response =>{
    personagens.value = response.results
    console.log(personagens)
  });
})
</script>

<style>
.conteiner{
  background-color: rgb(43, 43, 43)
}
</style>


<template>
  <main>
    <div class="conteiner ">
        <div class="row mt-8 justify-content-center " >
          <div class="col-md-12"  >
              <div class="cardy-body row">
                <ListCharacters 
                v-for="personagem in personagens"
                :key="personagem.id"
                :image="personagem.image"
                :status="personagem.status"
                :species="personagem.species"
                :gender="personagem.gender"
                :location="personagem.location"
                :name="personagem.name"
                :url="personagem.url"
                :episode="personagem.episode"
                />
              </div>  
          </div>
        </div>
    </div>
  </main>
</template>
