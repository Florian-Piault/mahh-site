<script setup>
import { ref } from "vue";
const selectedLang = ref("fr");
const selectedPage = ref("accueil");
const pages = [
  { name: "accueil" },
  { name: "programme" },
  { name: "collections" },
  { name: "visite" },
  { name: "le musée" },
  { name: "contact" },
  { name: "rechercher" },
];

const selectLang = lang => (selectedLang.value = lang);
const selectPage = page => (selectedPage.value = page);
</script>

<template>
  <header>
    <div class="langs">
      <button
        @click="selectLang('en')"
        class="btn btn-light"
        :class="{ 'btn-selected': selectedLang === 'en' }"
      >
        EN
      </button>
      |
      <button
        @click="selectLang('fr')"
        class="btn btn-light"
        :class="{ 'btn-selected': selectedLang === 'fr' }"
      >
        FR
      </button>
    </div>
    <img src="../assets/logo.svg" alt="" />
    <button class="btn btn-primary">Musée virtuel</button>
  </header>
  <nav>
    <ul>
      <li v-for="page in pages" :key="page + page.name">
        <button
          class="btn btn-light"
          :class="{ 'btn-selected': selectedPage === page.name }"
          @click="selectPage(page.name)"
        >
          {{ page.name[0].toUpperCase() + page.name.slice(1) }}
        </button>
      </li>
    </ul>
  </nav>
</template>

<style scoped></style>
