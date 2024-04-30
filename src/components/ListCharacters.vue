<script setup>
    const personagem = defineProps(["name", "status", "species", "gender", "location", "url", "image", "id", "episode" ])
    const imageUrl = personagem.image
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-4 card-custom" >
            <img :src="imageUrl" class="card-img-top img-fluid" alt="#" height="200"  >
            <div class="card-body "> 
                <p class="card-text ">Name: {{ personagem.name }}</p>
                <p class="card-text ">Status: {{ personagem.status }}</p>
                <p class="card-text ">Specie: {{ personagem.species }}</p>
                <p class="card-text ">Gender: {{ personagem.gender }}</p>
                <p class="card-text ">Location: {{ personagem.location.name }}</p>
                <p class="card-text ">Appeared in: {{ personagem.episode.length }} Episodes</p>
            </div>
        </div>
    </div>
</template>

<style>
.card-custom {
  background-color: rgb(195, 195, 195);
  border-color: rgb(0, 0, 0);
 
}

img {
    border-radius: 10%;
}
</style>