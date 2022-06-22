<script setup>
import Icon from "./Icon.vue";

// assets";
import frida from "../assets/collections/frida.png";
import frida2 from "../assets/collections/frida2.png";
import paysage from "../assets/collections/paysage.png";
import vangogh from "../assets/collections/vangogh.png";
import vangogh2 from "../assets/collections/vangogh2.png";
import vangogh3 from "../assets/collections/vangogh3.png";

const collections = [
  {
    id: 1,
    title: "Nom d'œuvre",
    name: "Frida Kahlo",
    date: "1920",
    image: frida,
  },
  {
    id: 2,
    title: "Nom d'œuvre",
    name: "Frida Kahlo",
    date: "1920",
    image: frida2,
  },
  {
    id: 3,
    title: "Vue de l’ermitage d’Albano",
    name: "Martin Verstappen",
    date: "1853",
    image: paysage,
  },
  {
    id: 4,
    title: "Nom d'œuvre",
    name: "Vincent Van Gogh",
    date: "1853",
    image: vangogh,
  },
  {
    id: 5,
    title: "Nom d'œuvre",
    name: "Vincent Van Gogh",
    date: "1853",
    image: vangogh2,
  },
  {
    id: 6,
    title: "Nom d'œuvre",
    name: "Vincent Van Gogh",
    date: "1853",
    image: vangogh3,
  },
];
</script>

<template>
  <div class="container">
    <div class="left">
      <h2>Explorez nos collections <span class="red">d'œuvres</span></h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam lectus
        fermentum arcu quam velit vitae vel imperdiet.
      </p>
    </div>
    <div class="right">
      <button class="btn btn-light red bigger">
        Collections
        <Icon icon="arrow-right" color="#d16465" />
      </button>
    </div>
  </div>
  <div class="collections">
    <div
      class="collection"
      v-for="collection in collections"
      :key="collection.id"
    >
      <div
        class="image"
        :style="'background-image: url(' + collection.image + ')'"
      ></div>
      <div class="info">
        <h3>{{ collection.title }}</h3>
        <p>{{ collection.name }}</p>
        <p>{{ collection.date }}</p>
      </div>
    </div>
  </div>
  <div class="action">
    <button class="btn btn-tertiary">Voir plus</button>
  </div>
</template>

<style scoped>
h2 {
  font-weight: 500;
  font-size: 2.25rem;
  margin-bottom: 2rem;
}
.red {
  color: var(--color-red);
}

.container {
  display: flex;
  flex-direction: row;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 5rem;
  height: auto;
}

.left {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  flex-wrap: wrap;
  align-items: flex-start;
  margin-left: 5rem;
  flex: 1;
  height: 100%;
}

.right {
  display: flex;
  justify-content: end;
  margin-right: 5rem;
  flex: 1;
}
.bigger {
  font-size: 1rem;
  font-weight: 600;
}

.collections {
  display: flex;
  flex-direction: row;
  align-items: center;
  flex-wrap: wrap;
  justify-content: center;
  margin-bottom: 5rem;
  height: auto;
  gap: 1rem;
}

.collection {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  flex-wrap: wrap;
  justify-content: flex-start;
  margin-bottom: 5rem;
  height: auto;
  width: clamp(20vw, 25rem, 90%);
}

.image {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  aspect-ratio: 16 / 9;
  width: 100%;
}

.collection:hover {
  transform: scale(1.1);
}

@media (max-width: 600px) {
  .container {
    flex-direction: column;
    gap: 2rem;
  }
  .left {
    flex-direction: row;
    margin-left: 1rem;
  }
  .right {
    justify-content: flex-start;
  }
}

.action {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 5rem;
}
</style>
