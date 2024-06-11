<script setup>
import { ref } from "vue";

const openIndex = ref(null);

const dropdowns = ref([
  {
    dropdown: "Digital konceptudvikling (1,5 år)",
    answer:
      "Som digital konceptudvikler udvikler du digitale brugeroplevelser på tværs af medier og platforme som fx websites, apps og markedsføringsmateriale. Du er bindeleddet mellem kunder og fagfolk, når programmering og teknik skal oversættes til forståeligt brugeroplevelser.",
  },
  {
    dropdown: "E-handel (1,5 år)",
    answer:
      "Med en professionsbacheloruddannelse i e-handel bliver du specialist i e-handel, digital økonomi og markedsføring samt andre onlinebaserede aktiviteter. Du bliver klædt på til at arbejde med customer experience, data-dreven markedsføring og creative content.",
  },
  {
    dropdown: "Innovation og entrepreneurship (1,5 år)",
    answer:
      "Som færdiguddannet bachelor i Innovation og Entrepreneurship har du mulighed for at starte egen virksomhed eller hjælpe andre virksomheder med at udvikle og omsætte deres forretningsidéer.",
  },
  {
    dropdown: "Webudvikling (1,5 år)",
    answer:
      "Uddannelsen i webudvikling er for dig, der vil arbejde kreativt med kodning og specialisere dig inden for udviklingen af apps, hjemmesider og andre webløsninger. Undervejs på uddannelsen til webudvikling vil du komme til at arbejde med teknologier, der klæder dig på til at kunne indgå i mange typer af jobs.",
  },
]);

function toggleDropdown(index) {
  openIndex.value = openIndex.value === index ? null : index;
}
</script>

<template>
  <section id="imScroll">
    <div class="buttom-divider" id="none">
      <div class="buttom-divider-width talentprogram-img"></div>
      <div class="buttom-divider-width">
        <h2>Talent program</h2>
        <p>
          UCL’s talentprogram er baseret på mulighederne for, at talentfulde
          studerende kan opnå anerkendelse for talent som et tillæg til deres
          eksamensbevis.
        </p>
        <div class="btn-green">
          <p>Talentprogram</p>
          <svg
            class="arrow"
            xmlns="http://www.w3.org/2000/svg"
            width="6.473"
            height="10.982"
            viewBox="0 0 6.473 10.982"
          >
            <path
              id="Icon_material-arrow-back-ios"
              data-name="Icon material-arrow-back-ios"
              d="M6.473.982,5.491,0,0,5.491l5.491,5.491L6.473,10,1.963,5.491Z"
              transform="translate(6.473 10.982) rotate(180)"
              fill="#FAE76A"
            />
          </svg>
        </div>
      </div>
    </div>
  </section>
  <section>
    <h3>Byg ovenpå uddannelsen og bliv bachelor</h3>
    <div class="buttom-divider">
      <div class="buttom-divider-width">
        <p>
          Efter endt uddannelse har du mulighed for at tage en top-up
          uddannelse, som kan give dig flere karrieremuligheder og specialisere
          din viden inden for et specifikt område. Til højre finder du dine
          fremtidige muligheder. Du kan for eksempel vælge at videreuddanne dig
          inden for:
        </p>
      </div>
      <div class="buttom-divider-width">
        <div class="item-wrap">
          <div class="dropdown-wrap" v-for="(item, index) in dropdowns">
            <div class="dropdown" @click="toggleDropdown(index)">
              <h3>{{ item.dropdown }}</h3>
              <img src="../assets/img/arrow-down.svg" alt="arrow" />
            </div>
            <div class="answer" v-if="openIndex === index">
              <p>{{ item.answer }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.dropdown-wrap {
  margin-top: 5px;
  background-color: #fff;
  border: 1px solid #00454e;
  width: 100%;
  cursor: pointer;
}

.dropdown {
  display: flex;
  justify-content: space-between;
  padding: 15px;
}

.answer {
  padding: 15px;
}

.talentprogram-img {
  background-image: url("../assets/img/talentprogram.png");
  background-size: cover;
  height: 250px;
}

.talentprogram-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.arrow {
  fill: #fae76a;
  display: flex;
  align-items: center;
}

.dropdown-wrap:hover {
  background-color: #e2f1ee;
}
</style>
