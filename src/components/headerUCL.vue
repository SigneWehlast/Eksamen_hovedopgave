<template>
  <nav>
    <header>
      <div class="logo-div">
        <a href="">
          <img
            class="logo"
            src="../assets/img/mitucl-logo.png"
            alt="MitUcl logo"
          />
        </a>
        <div class="burger-div">
          <button class="burger-search">
            Søg <img src="../assets/img/search-icon-dark.svg" alt="Søge knap" />
          </button>
          <button class="burgermenu" @click="toggleMenu">
            <img src="../assets/img/burgermenu-icon.svg" alt="" />
          </button>
        </div>
      </div>
      <div :class="['nav-wrap', { open: isMenuOpen }]">
        <div class="top-nav-wrap">
          <ul class="top-nav">
            <li>GDPR - behandling af persondata</li>
            <li>Krisesituationer på UCL</li>
            <li>mitUCL på mobilen</li>
            <li>Bibliotek</li>
          </ul>
          <button class="search-btn">
            Søg
            <img src="../assets/img/search-icon-white.svg" alt="Søge knap" />
          </button>
          <button class="pen-btn">
            Tilpas valg
            <img src="../assets/img/pen-icon-green.svg" alt="Tilpas knap" />
          </button>
        </div>
        <div class="buttom-nav-wrap">
          <ul class="buttom-nav">
            <li>Mit campus</li>
            <!--midlertidig løsning ind til karrierevejledning-->
            <li
              id="studieservice"
              @mouseenter="showDropdown"
              @mouseleave="hideDropdown"
            >
              <router-link to="">Studieservice</router-link>
              <ul v-show="isDropdownOpen" class="dropdown-menu">
                <li><router-link to="">Studiestart</router-link></li>
                <li><router-link to="/">Studieadministration</router-link></li>
                <li><router-link to="/">SU-vejledning</router-link></li>
                <li><router-link to="/">Studievejledning</router-link></li>
                <li><router-link to="/">SPS-vejledning</router-link></li>
                <li>
                  <router-link to="/karrierevejledning"
                    >Karrierevejledning</router-link
                  >
                </li>
                <li><router-link to="/">Service portalen</router-link></li>
                <li>
                  <router-link to="">Internationale muligheder</router-link>
                </li>
                <li><router-link to="/">Krisesituationer</router-link></li>
              </ul>
            </li>
            <li>Events & studieliv</li>
            <li>SU</li>
            <li>Specialpædagogisk støtte (SPS)</li>
          </ul>
        </div>
      </div>
    </header>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
      isDropdownOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    showDropdown() {
      this.isDropdownOpen = true;
    },
    hideDropdown() {
      this.isDropdownOpen = false;
    },
  },
};
</script>

<style scoped>
nav {
  background-color: #e6f1f0;
  padding-top: 5%;
  width: 100%;
  max-width: 1200px;
}

header {
  display: flex;
  justify-content: space-between;
}

.logo {
  width: 250px;
}

.nav-wrap {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 15px;
}

.top-nav-wrap {
  display: flex;
  align-items: center;
  gap: 30px;
}

.top-nav {
  display: flex;
  gap: 30px;
  font-size: 11px;
}

li {
  list-style-type: none;
}

a {
  text-decoration: none;
  color: #00454e;
  position: relative;
}

li a::after {
  content: "";
  position: absolute;
  width: 0;
  height: 3px;
  background-color: #00454e;
  bottom: 0;
  left: 0;
  transition: width 0.3s ease-in-out;
}
li a:hover::after {
  width: 20%;
}

#studieservice li a:hover::after {
  width: 20%;
}

#studieservice li a::after {
  content: "";
  position: absolute;
  width: 0;
  height: 3px;
  background-color: #fff;
  bottom: 0;
  left: 0;
  transition: width 0.3s ease-in-out;
}

li {
  text-align: left;
}

.search-btn {
  background-color: #00454e;
  color: #ffffff;
  border-radius: 7px;
  border: none;
  padding: 6px 12px;
  gap: 5px;
  display: flex;
  align-items: center;
}

.pen-btn {
  background-color: #e6f1f0;
  color: #00454e;
  border-radius: 7px;
  border: solid 1px #00454e;
  padding: 6px 12px;
  gap: 5px;
  display: flex;
  align-items: center;
}

.buttom-nav-wrap {
  display: flex;
  justify-content: flex-end;
}

.buttom-nav {
  display: flex;
  gap: 30px;
  font-size: 16px;
  font-weight: bold;
}

.burger-div {
  display: none;
}

.dropdown-menu {
  display: none;
  position: absolute;
  background-color: #00454e;
  padding: 10px;
  list-style: none;
  margin: 10;
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.1);
  z-index: 1;
}

.dropdown-menu li {
  padding: 8px 12px;
}

.dropdown-menu li a {
  margin-top: 5px;
  color: #fff;
  text-decoration: none;
}

.buttom-nav li:hover .dropdown-menu {
  display: block;
  margin-top: 1px;
}

/* Responsive styles */

@media screen and (max-width: 1100px) {
  .dropdown-menu {
    position: relative;
    box-shadow: none;
  }
}

@media screen and (max-width: 1200px) {
  header {
    padding: 0 5%;
  }

  .logo {
    width: 200px;
  }
}

@media screen and (max-width: 1100px) {
  .logo-div {
    background-color: #e6f1f0;
    padding: 3%;
    box-sizing: border-box;
  }

  .nav-wrap {
    flex-direction: column-reverse;
    width: 100%;
    height: 100vh;
    justify-content: flex-end;
    right: -106%;
    position: relative;
    padding: 3%;
    box-sizing: border-box;
    top: 50px;
    display: none;
  }

  .nav-wrap.open {
    right: 0;
    background-color: #e6f1f0;
    display: flex;
  }

  .buttom-nav-wrap {
    justify-content: flex-start;
  }

  .buttom-nav {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }

  .top-nav-wrap {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    align-items: flex-end;
    justify-content: space-between;
  }

  .top-nav {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }

  nav {
    padding: 0;
    padding-bottom: 2%;
    position: fixed;
    z-index: 2;
    margin-top: 0;
    background-color: transparent;
  }

  header {
    flex-direction: column;
    align-items: flex-start;
    padding: 0;
  }

  .burgermenu {
    display: flex;
    border-radius: 100%;
    padding: 15px;
    border-style: none;
    background-color: #00454e;
  }

  .logo-div {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }

  .burger-div {
    display: flex;
    gap: 20px;
  }

  .burger-search {
    display: flex;
    align-items: center;
    gap: 10px;
    background-color: #ffffff;
    border-radius: 50px;
    border-style: none;
    padding: 0 20px;
  }

  .search-btn {
    display: none;
  }
}

@media screen and (max-width: 465px) {
  .logo {
    width: 150px;
  }
}
</style>
