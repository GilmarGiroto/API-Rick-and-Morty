<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

let personagens = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character/?page=1")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-12">
          <div class="card">
            <div class="card-body row">
              <ListPersonagens 
                v-for="personagem in personagens" 
                :key="personagem.name" 
                :name="personagem.name"
                :url="personagem.url"
                :status="personagem.status"
                :specie="personagem.species"
                :gender="personagem.gender"
                :location="personagem.location.name"
                :episode="personagem.episode"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
