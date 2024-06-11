<script setup>
import { ref } from "vue";

const openIndex = ref(null);

const dropdowns = ref([
  {
    dropdown: "Om praktikken",
    answer:
      "Praktikperioden på uddannelsen til multimediedesigner er din chance for at få prøvet din nyerhvervede viden af i den virkelige verden, hvor du får mulighed for at varetage samme opgaver som en færdiguddannet multimediedesigner. <br><br>Du udvikler dig både fagligt og personligt under praktikperioden og får et godt billede af, hvad du vil med din uddannelse, når du er færdig.  <br><br>Dine erfaringer fra praksis er meget værdifulde, når du skal ud på jobmarkedet efter endt uddannelse. Du har ikke bare læst en masse teorier, men du har rent faktisk prøvet at arbejde inden for det område, som din uddannelse sigter mod.  <br><br>En praktikplads er desuden en enestående chance for at udvide dit netværk i erhvervslivet og er ofte en direkte vej ind på arbejdsmarkedet efter studiet. <br><br>Du har også mulighed for at tage din praktik i udlandet.",
  },
  {
    dropdown: "Jobportalen",
    answer:
      "Du kan altid finde annoncerede praktikmuligheder på jobportalen. Ud over studiejobs og dimittendjobs indeholder jobportalen også praktikmuligheder annonceret direkte til dig. <br> <br> <i><b> - Læs mere på Jobportalen</b></i>",
  },
  {
    dropdown: "Praktikfaktaark og praktikportal",
    answer:
      "<b>Praktikfaktaark</b> <br>Har du helt styr på, hvad det egentlig er, du kan tilbyde din kommende praktikvært?<br><br> Find dit praktikfaktaark og bliv helt skarp på dine kompetencer, når du skal ud og søge praktikplads. <br><br> <b><i>- Find dit praktikfaktaark </i></b> <br><br> <b>Praktikportalen</b> <br>Dit praktikophold administreres i Praktikportalen. <br><br>I praktikportalen kan du bl.a. ønske praktikpladser, kommunikere med praktikstedet, se praktikrelevante dokumenter, m.m.  <br><br> <b><i>- Læs mere om Praktikportalen </b></i>",
  },
  {
    dropdown: "Ikke gennemført praktik",
    answer:
      "Hvis du starter i praktik, men praktikken bliver afbrudt eller ikke kan godkendes som gennemført, risikerer du at modtage et varslingsbrev om udmeldelse, fordi du kun har ret til én praktikplads pr. praktikforløb, jfr.<br><br> <b><i>- Eksamensbekendtgørelsens § 5</i></b> <br><br>Af varslingsbrevet vil fremgå en mulighed for at søge om dispensation til en ekstra praktik, hvis du kan dokumentere, at der foreligger usædvanlige forhold. Læs mere om <br><br> <b><i>- Dispensation </i></b><br><br> Det samme gælder, hvis du ikke finder en praktikplads inden for de tidsfrister, der er fastsat på din uddannelse. Det er derfor vigtigt, at du i god tid kontakter uddannelsen for at få hjælp til praktikplads-søgning, hvis du har svært ved at finde en praktikplads på egen hånd.<br><br> Hvis din praktik er godkendt og du derfor er blevet indstillet til praktikeksamen, kan der ikke dispenseres til ny praktik trods brugte eksamensforsøg.",
  },
  {
    dropdown: "Få hjælp",
    answer:
      "Du kan få hjælp til alt inden for praktik og jobsøgning hos karrierevejledningen på UCL. Du kan læse mere om, hvordan de kan hjælpe dig og hvilke tilbud de udbyder her:<br><br> <b><i>- <a href='#/karrierevejledning' class='no-decoration'>Karrierevejledningen</a> </i></b> <br><br> Find online guides der kan hjælpe dig med din ansøgning, CV, kompetence-afklaring m.m. her: <br><br> <i><b>- Online guides</a> </b></i>",
  },
]);

function toggleDropdown(index) {
  openIndex.value = openIndex.value === index ? null : index;
}

function isOpen(index) {
  return openIndex.value === index;
}
</script>

<template>
  <section id="praktik-scroll">
    <h2>Praktik</h2>
    <div class="buttom-divider" id="none">
      <div class="buttom-divider-width">
        <p>Dit praktikforløb er af 3 måneders varighed.</p>
        <ul>
          <li>Praktikken finder sted på 4. semester.</li>
          <li>Du er selv ansvarlig for at finde en praktikplads.</li>
          <li>Praktikperioden er ulønnet og SU-berettiget</li>
        </ul>
      </div>
      <div class="buttom-divider-width">
        <div class="item-wrap">
          <div class="dropdown-wrap" v-for="(item, index) in dropdowns" :key="index">
            <div class="dropdown" @click="toggleDropdown(index)">
              <h3>{{ item.dropdown }}</h3>
              <img src="../assets/img/arrow-down.svg" alt="arrow" />
            </div>
            <div class="answer_uo" v-if="isOpen(index)">
              <p v-html="item.answer"></p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="buttom-divider">
      <div class="buttom-divider-width">
        <div class="blue-card">
          <h3>Kontakt din praktikkoordinator</h3>
          <div class="card-inner">
            <img
              class="profile-img"
              src="../assets/img/praktikkoordinator.png"
              alt="Prkatik koordinator profil billede"
            />
            <div class="koordinator-info">
              <h4>Karen Malene Andreasen</h4>
              <p>Praktikkordinator</p>
              <div class="list">
                <img src="../assets/img/phone-icon.svg" alt="" />
                <p>22 66 02 86</p>
              </div>
              <div class="list">
                <img src="../assets/img/mail-icon.svg" alt="" />
                <p>kmea@ucl.dk</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="buttom-divider-width">
        <h3>To vejledere</h3>
        <p>
          I praktikken har du både en vejleder på dit praktiksted og en vejleder
          fra uddannelsesinstitutionen. De følger og vejleder dig begge to i de
          3 måneder, du er i praktik. Din praktikvejleder på UCL fremgår her på
          siden mens du først får tildelt en vejleder på dit praktiksted, når
          din praktikaftale foreligger.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.dropdown-wrap {
  margin-top: 5px;
  background-color: #daeced;
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

.card-inner {
  display: flex;
  gap: 20px;
  margin-top: 40px;
}

.profile-img {
  width: 100px;
  height: 100px;
}

.no-decoration {
  text-decoration: none;
}

#none {
  border-bottom: none;
}
</style>
