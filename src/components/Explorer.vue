<template>
  <section>
    <div class="title">
      <h1>Explorez nos célébrités</h1>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam lectus
        fermentum arcu quam velit vitae vel imperdiet.
      </p>
    </div>
    <div class="carrousel">
      <div v-for="celebrite in celebrites" :key="celebrite.id" class="card">
        <div>
          <img :src="celebrite.image" :alt="'Image de ' + celebrite.name" />
          <p class="name">{{ celebrite.name }}</p>
        </div>
      </div>
    </div>
    <button class="btn btn-light">
      <Icon icon="arrow-right" />
    </button>
  </section>
</template>
<script setup>
import celebrite1 from "../assets/scroll/john.png";
import celebrite2 from "../assets/scroll/frida.png";
import celebrite3 from "../assets/scroll/ray.png";
import celebrite4 from "../assets/scroll/henri.png";
import celebrite5 from "../assets/scroll/stephen.png";
import Icon from "./Icon.vue";

const celebrites = [
  {
    id: 1,
    name: "John Nash",
    image: celebrite1,
  },
  {
    id: 2,
    name: "Frida Kahlo",
    image: celebrite2,
  },
  {
    id: 3,
    name: "Ray Charles",
    image: celebrite3,
  },
  {
    id: 4,
    name: "Henri de Toulouse-Lautrec",
    image: celebrite4,
  },
  {
    id: 5,
    name: "Stephen Hawking",
    image: celebrite5,
  },
];
</script>
<style scoped>
section {
  margin-bottom: 5rem;
  height: 100vh;
  background-color: #d3b67d;
  position: relative;
}
section > button {
  position: absolute;
  right: 0;
  margin-right: 6.25rem;
  bottom: 0;
  margin-bottom: 5rem;
}
.title {
  text-align: left;
  padding-left: 4.875rem;
  padding-top: 6.563rem;
  color: black;
  font-style: normal;
}
.title > h1 {
  font-size: 68px;
}
.title > p {
  font-size: 16px;
}
.carrousel {
  display: flex;
  flex-direction: row;
  align-items: center;
  /* justify-content: space-between; */
  overflow-y: scroll;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  margin-top: 4.313rem;
}
.carrousel > .card {
  margin: 0 1.688rem 0 1.688rem;
}

.carrousel .name {
  padding-top: 1.25rem;
  text-align: center;
  font-weight: bold;
  font-size: 1.25rem;
}

.carrousel::-webkit-scrollbar {
  display: none;
}
</style>
