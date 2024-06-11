<template>
  <nav>
    <div class="nav-inner" @click="toggleNav">
      <div>
        <h3 class="h-white">Karrierevejledningen</h3>
        <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
      </div>

      <ul :class="{ 'nav-open': isNavOpen }">
        <li id="nav-hkvt" @click="scrollToElement('hkvt')">
          Hvad kan vi tilbyde?
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-bdk" @click="scrollToElement('bdk')">
          Book en vejledning
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-tjekliste" @click="scrollToElement('tjekliste')">
          Karriere tjekliste
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-hsds" @click="scrollToElement('hsds')">
          Hvad siger de studerende?
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-jobp" @click="scrollToElement('jobp')">
          Jobportalen
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-arrang" @click="scrollToElement('arrang')">
          Arrangementer
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
        <li id="nav-kontaktka" @click="scrollToElement('kontaktka')">
          Kontakt karrierevejledningen
          <img class="mobile-arrow" src="../assets/img/arrow-white.svg" alt="" />
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const isNavOpen = ref(false);

const toggleNav = () => {
  isNavOpen.value = !isNavOpen.value;
};

const scrollToElement = (elementId) => {
  document.getElementById(elementId).scrollIntoView({ behavior: "smooth" });
};

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  const offset = 100; // Offset for aktivitetsændring
  const sectionIds = ['hkvt', 'bdk', 'tjekliste', 'hsds', 'jobp', 'arrang', 'kontaktka']; // Liste over afsnit id'er

  sectionIds.forEach((sectionId) => {
    const section = document.getElementById(sectionId);
    if (!section) return;

    const sectionTop = section.offsetTop;
    const sectionHeight = section.offsetHeight;

    if (scrollPosition >= sectionTop - offset && scrollPosition < sectionTop + sectionHeight - offset) {
      setActiveNavItem(sectionId);
    }
  });
};

const setActiveNavItem = (itemId) => {
  const navItems = document.querySelectorAll("ul li");
  navItems.forEach((item) => {
    item.style.opacity = item.id === `nav-${itemId}` ? '1' : '0.5';
  });
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  // Aktiver det første navigationspunkt ved starten
  setActiveNavItem('hkvt');
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
/* Your existing styles remain unchanged */

#nav-hkvt {
  opacity: 1; /* Initially set the first item as active */
}

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
