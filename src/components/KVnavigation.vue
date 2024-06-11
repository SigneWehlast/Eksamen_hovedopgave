<script setup>
import { ref } from "vue";

const isNavOpen = ref(false);

const toggleNav = () => {
  isNavOpen.value = !isNavOpen.value;
};

const hkvtScroll = () => {
  document.getElementById("hkvt").scrollIntoView({ behavior: "smooth" });
};

const bdkScroll = () => {
  document.getElementById("bdk").scrollIntoView({ behavior: "smooth" });
};

const tjeklisteScroll = () => {
  document
    .getElementById("tjekliste-baggrund")
    .scrollIntoView({ behavior: "smooth" });
};

const hsdsScroll = () => {
  document
    .getElementById("reviews_section")
    .scrollIntoView({ behavior: "smooth" });
};

const jobpScroll = () => {
  document.getElementById("jobp").scrollIntoView({ behavior: "smooth" });
};

const arrangScroll = () => {
  document.getElementById("arrang").scrollIntoView({ behavior: "smooth" });
};

const kontaktkaScroll = () => {
  document.getElementById("kontaktka").scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <nav>
    <div class="nav-inner" @click="toggleNav">
      <div>
        <h3 class="h-white">Karrierevejledningen</h3>
        <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
      </div>

      <ul :class="{ 'nav-open': isNavOpen }">
        <li @click="hkvtScroll()">
          Hvad kan vi tilbyde?
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="bdkScroll()">
          Book en vejledning
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="tjeklisteScroll()">
          Karriere tjekliste
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="hsdsScroll()">
          Hvad siger de studerende?
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="jobpScroll()">
          Jobportalen
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="arrangScroll()">
          Arrangementer
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
        <li @click="kontaktkaScroll()">
          Kontakt karrierevejledningen
          <img
            class="mobile-arrow"
            src="../assets/img/arrow-white.svg"
            alt=""
          />
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
  position: sticky;
  left: 0px;
  top: 0px;
  padding: 40px;
  box-sizing: border-box;
  background-color: #00454e;
  margin-top: 0;
  background: url("../assets/img/background.png") center 50%;
}

.nav-inner {
  color: white;
  text-wrap: nowrap;
  cursor: pointer;
}

ul {
  display: flex;
  flex-direction: column;
  list-style-type: none;
  font-size: 15px;
  font-weight: bold;
  gap: 60px;
}

.mobile-arrow {
  display: none;
}

.nav-inner h3 {
  color: #47b9b3;
}

.nav-inner div {
  margin-bottom: 70px;
}

@media screen and (max-width: 1100px) {
  nav {
    height: auto;
    position: fixed;
    top: 125px;
    width: 100%;
    padding: 20px;
    z-index: 99;
  }

  .nav-inner h3 {
    color: #47b9b3;
  }

  .nav-inner div {
    display: flex;
    justify-content: space-between;
    align-items: flex-center;
    gap: 10px;
    margin-bottom: 0;
  }

  .mobile-arrow {
    width: 10px;
    align-items: center;
    display: block;
  }

  ul {
    gap: 30px;
    display: none;
    transition: max-height 0.3s ease-in-out;
    max-height: 0;
    overflow: hidden;
  }

  ul.nav-open {
    display: flex;
    max-height: 500px;
    margin-top: 30px;
  }
}

li {
  display: flex;
  justify-content: space-between;
}

@media screen and (max-width: 465px) {
  nav {
    top: 100px;
  }
}
</style>
