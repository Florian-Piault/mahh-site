<script setup>
import Icon from "./Icon.vue";
import { ref } from "vue";
import expo1 from "../assets/expo1.png";
import expo2 from "../assets/expo2.png";
import expo3 from "../assets/expo3.png";
const actualExpoIndex = ref(0);
const expositions = [
  {
    id: 0,
    title: "Les impressionnistes au-delà des normes",
    date: "Du 23 août au 26 novembre",
    image: expo1,
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehe",
  },
  {
    id: 1,
    title: "Exposition Ray Charles",
    date: "Du 15 décembre au 2 février",
    image: expo2,
    description:
      "Pa alias quaerat qui rerum voluptatem sed galisum inventore et eius possimus aut perferendis quod qui iste veniam. Qui sint voluptas sit expedita autem non consequuntur adipisci. Aut aliquam dolorum 33 nihil esse non facilis blanditiis At adipisci repudiandae. Ut similique aspernatur est susc",
  },
  {
    id: 2,
    title: "La vie de Frida Kahlo",
    date: "Du 4 mars au 12 juin",
    image: expo3,
    description:
      "Et laudantium incidunt qui quaerat esse est atque eius qui reiciendis rerum ad reprehenderit sunt! Non sunt quia At quam recusandae ad perspiciatis voluptates qui voluptas incidunt eum galisum quia aut",
  },
  {
    id: 3,
    title: "Les impressionnistes au-delà des normes",
    date: "Du 23 août au 26 novembre",
    image: expo1,
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehe",
  },
  {
    id: 4,
    title: "Les impressionnistes au-delà des normes",
    date: "Du 23 août au 26 novembre",
    image: expo1,
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehe",
  },
];

const nextExpo = () =>
  (actualExpoIndex.value = (actualExpoIndex.value + 1) % expositions.length);
const prevExpo = () =>
  (actualExpoIndex.value =
    (actualExpoIndex.value - 1 + expositions.length) % expositions.length);
</script>

<template>
  <div class="expo">
    <div class="left">
      <h2><b>Expositions</b> temporaires</h2>
      <div class="card">
        <p class="card-date">{{ expositions[actualExpoIndex].date }}</p>
        <h3 class="card-title">{{ expositions[actualExpoIndex].title }}</h3>
        <p class="card-description">
          {{ expositions[actualExpoIndex].description }}
        </p>
      </div>
      <button class="btn btn-secondary">
        Visiter
        <Icon icon="arrow-right" color="white" />
      </button>
    </div>
    <div class="right">
      <div
        class="expo-img"
        :style="
          'background-image: url(' + expositions[actualExpoIndex].image + ')'
        "
      ></div>
    </div>
  </div>
  <div class="pagination">
    <button class="btn btn-light" @click="prevExpo">
      <Icon icon="arrow-left" color="#5a65d1" />
    </button>
    <div class="dots">
      <Icon
        v-for="exposition in expositions"
        :key="exposition.id"
        icon="dot"
        :color="actualExpoIndex === exposition.id ? '#d3b67d' : '#5a65d1'"
      />
    </div>
    <button class="btn btn-light" @click="nextExpo">
      <Icon icon="arrow-right" color="#5a65d1" />
    </button>
  </div>
</template>

<style scoped>
.expo {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 5rem;
  height: 80vh;
}

h2 {
  font-weight: 500;
  font-size: 2.25rem;
  margin-bottom: 2rem;
}
b {
  color: var(--color-blue);
}

.carousel-controls {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  margin-bottom: 2rem;
}
.arrows {
  display: flex;
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

.expo-img {
  /* background-image: url("../assets/expo1.png"); */
  background-size: cover;
  background-position: center;
  height: 35vw;
  width: 30vw;
  border-top-left-radius: 100vmax;
  border-top-right-radius: 100vmax;
}

.btn-secondary {
  background-color: var(--color-blue);
  color: white;
}

.card {
  width: 80%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 1rem;
}
.card-date {
  font-weight: lighter;
  font-size: 0.9rem;
  color: rgba(0, 0, 0, 0.6);
}

.card-title {
  font-style: italic;
}

.btn-secondary {
  margin-top: 1rem;
  font-size: 1rem;
}

.pagination {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  margin-bottom: 5rem;
}
</style>
