<template>
  <section>
    <div class="menu liste1">
      <ul>
        <li><h3>NOS SITES</h3></li>
        <li>Billeterie</li>
        <li>Programme</li>
        <li>Collections</li>
        <li>Le musée</li>
        <li>Contact</li>
      </ul>
    </div>
    <div class="menu liste2">
      <ul>
        <li><h3>MUSÉE VIRTUEL</h3></li>
        <li>Accès métavers</li>
        <li>À propos</li>
        <li>Conditions</li>
      </ul>
    </div>
    <div class="menu reseaux">
      <div class="section follow">
        <h3>SUIVEZ-NOUS</h3>
        <div class="icons">
          <a href=""><Icon icon="facebook" /></a>

          <a href=""><Icon icon="instagram" /></a>

          <a href=""><Icon icon="twitter" /></a>

          <a href=""><Icon icon="youtube" /></a>

          <a href=""><Icon icon="linkedin" /></a>
        </div>
      </div>
      <div class="section newsletter">
        <h3>NEWSLETTER</h3>
        <input type="text" name="newsletter" id="newsletter" />
      </div>
    </div>
    <div class="logo">
      <Icon icon="logo" />
      <p>Musée d’Art et d’Histoire du Handicap</p>
    </div>
    <div class="mentions">
      <p>Mentions légales</p>
      <p>Données personnelles</p>
      <p>Cookies</p>
      <p>Accessibilité</p>
      <p>Crédits</p>
      <p>Crédits photographiques</p>
    </div>
  </section>
</template>
<style scoped>
section {
  height: 85vh;
  background-color: black;
  display: grid;
  grid-template-columns: 1fr 1fr 2fr;
  grid-template-rows: 1fr 83px 0.4fr;
  gap: 0px 0px;
  grid-auto-flow: row;
  grid-template-areas:
    ". . ."
    ". . ."
    ". . .";
}
.logo {
  grid-column-start: 1;
  grid-column-end: span 3;
  justify-self: center;
  display: inline-flex;
  align-self: end;
}
.logo > p {
  color: white;
  width: 92px;
  align-self: end;
}
.mentions {
  grid-column-start: 1;
  grid-column-end: span 3;
  color: white;
  align-self: center;
  justify-self: center;
  display: flex;
  justify-content: end;
}
.mentions > p {
  margin-left: 5rem;
}
.menu {
  color: white;
  justify-self: center;
  padding-top: 4.813rem;
}
.menu > ul {
  list-style: none;
}
.menu > ul > li {
  padding-bottom: 1.563rem;
}
.reseaux {
  justify-self: start;
}
.reseaux > div > h3 {
  color: white;
  margin-bottom: 1.5rem;
}
.reseaux > .follow > .icons {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 3.125rem;
}
</style>
<script setup>
import Icon from "./Icon.vue";
</script>
