<template>
  <nav>
    <div class="nav-inner" @click="toggleNav">
      <div>
        <h3 class="h-white">Karrierevejledningen</h3>
        <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
      </div>

      <ul :class="{ 'nav-open': isNavOpen }">
        <li
          v-for="section in sections"
          :key="section.id"
          :id="`nav-${section.id}`"
          :class="{ active: activeSection === section.id }"
          @click="scrollToElement(section.id)"
        >
          {{ section.label }}
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const isNavOpen = ref(false);
const activeSection = ref("hkvt");

const sections = [
  { id: "hkvt", label: "Hvad kan vi tilbyde?" },
  { id: "bdk", label: "Book en vejledning" },
  { id: "tjekliste", label: "Karriere tjekliste" },
  { id: "hsds", label: "Hvad siger de studerende?" },
  { id: "jobp", label: "Jobportalen" },
  { id: "arrang", label: "Arrangementer" },
  { id: "kontaktka", label: "Kontakt karrierevejledningen" },
];

const toggleNav = () => {
  isNavOpen.value = !isNavOpen.value;
};

const scrollToElement = (elementId) => {
  document.getElementById(elementId).scrollIntoView({ behavior: "smooth" });
};

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  const offset = 100; // Offset for aktivitetsændring

  sections.forEach((section) => {
    const element = document.getElementById(section.id);
    if (!element) return;

    const sectionTop = element.offsetTop;
    const sectionHeight = element.offsetHeight;

    if (scrollPosition >= sectionTop - offset && scrollPosition < sectionTop + sectionHeight - offset) {
      activeSection.value = section.id;
    }
  });
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  // Aktiver det første navigationspunkt ved starten
  activeSection.value = 'hkvt';
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

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
  opacity: 0.5;
  transition: opacity 0.3s ease;
}

li.active {
  opacity: 1;
}

@media screen and (max-width: 465px) {
  nav {
    top: 100px;
  }
}
</style>
