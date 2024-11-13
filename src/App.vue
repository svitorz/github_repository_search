<template>
  <div class="w-full h-screen">
    <div class="flex justify-center items-center">
      <input v-model="username" name="username" id="username" type="text"
        class="rounded border-black border my-5 p-5 rounded-e-none border-e-0 focus:ring-black focus:ring-2 outline-none focus:outline-none"
        placeholder="Github username" />
      <button
        class="border-s-0 p-5 bg-black text-white border rounded rounded-s-none  active:text-black active:bg-slate-500 hover:bg-gray-700 "
        id="submit_button" type="button" @click.prevent="fetchRepos">
        Search for repo's
      </button>
    </div>
    <div class="flex justify-center items-center">
      <div v-if="loading" class="loader my-5"></div> <!-- Aqui, o loader será exibido quando loading for true -->
      <div v-if="error" class="my-5 text-red-500">{{ error }}</div> <!-- Mensagem de erro será exibida -->
      <div v-if="repos.length > 0">
        <h3 class="text-center text-black">Repos encontrados</h3>
        <div class="container mx-auto p-4">
          <div class="grid grid-cols-1 gap-4 md:grid-cols-2 lg:grid-cols-4">
            <div class="bg-white hover:bg-black hover:text-white rounded-lg shadow-md p-6" v-for="repo in repos"
              :key="repo.id">
              <a :href="'https://github.com/' + repo.owner.login + '/' + repo.name" target="_blank">
                <h3 class="text-lg font-semibold mb-2">{{ repo.name }}</h3>
                <p class="text-gray-600 hover:text-gray-50">{{ repo.description }}</p>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const username = ref('');
const repos = ref([]);
const error = ref(null);
const loading = ref(false);

const fetchRepos = async () => {
  repos.value = [];
  try {
    if (username.value.trim() === '') {
      error.value = "Você deve inserir um nome de usuário.";
      loading.value = false;
      return;  // Interrompe a execução e impede que o loader apareça
    }

    loading.value = true;  // Define loading como true para exibir o loader
    error.value = null;  // Limpa qualquer erro anterior
    const url = `https://api.github.com/users/${username.value}/repos`;
    const response = await fetch(url);
    if (!response.ok) {
      error.value = "Erro ao buscar repositórios.";
      console.log("Erro ao buscar repositórios.");
      throw new Error('Erro ao buscar repos.');
    }

    repos.value = await response.json();
    console.log(repos.value);
  } catch (err) {
    error.value = err.message;
  } finally {
    loading.value = false;  // Ao terminar, setamos o loading para false
  }
}
</script>

<style scoped>
.loader {
  width: 50px;
  aspect-ratio: 1;
  border-radius: 50%;
  border: 8px solid;
  border-color: #000 #0000;
  animation: l1 1s infinite;
}

@keyframes l1 {
  to {
    transform: rotate(.5turn);
  }
}
</style>
