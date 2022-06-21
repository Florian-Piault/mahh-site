<script setup>
import Icon from "./Icon.vue";
</script>

<template>
  <div class="expo">
    <div class="left">
      <div>
        <h2><b>Exposition</b> éphémères</h2>
        <div class="carousel-controls">
          <div class="arrows">
            <button class="btn btn-light">
              <Icon icon="arrow-left" />
            </button>
            <button class="btn btn-light">
              <Icon icon="arrow-right" />
            </button>
          </div>
          <p class="carousel-indactor">03/08</p>
        </div>
      </div>
      <div class="card">
        <p class="card-date">Du 23 août au 26 novembre</p>
        <h3 class="card-title">Les impressionnistes au-delà des normes</h3>
        <p class="card-description">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Habitant
          integer sapien proin nunc, purus donec pretium. Vel duis scelerisque
          nibh cursus facilisi.
        </p>
        <button class="btn btn-secondary">
          Visiter
          <Icon icon="arrow-right" color="white" />
        </button>
      </div>
    </div>
    <div class="right">
      <div class="expo-img"></div>
    </div>
  </div>
  <div class="timeline"></div>
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
  background-image: url("../assets/expo1.png");
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
}
</style>
