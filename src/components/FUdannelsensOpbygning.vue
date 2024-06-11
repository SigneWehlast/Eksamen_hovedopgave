<script setup>
import { ref } from "vue";

const openIndex = ref(null);

const openIndex2 = ref(null);

const dropdowns = ref([
  {
    dropdown: "Fællesdel",
    answer:
      "Uddannelsen til multimediedesigner består af en fælles del og en specialiseringsdel. <br> Fællesdelen er ens for alle uanset hvilken specialering, du vælger. Her lærer du om: <br><ul><li>Brugergrænseflader</li><li>Brugeroplevelse</li><li>Indholdsproduktion</li><li>Forretningsforståelse</li><li>Teknologi</li></ul>",
  },
  {
    dropdown: "Specialisering",
    answer:
      "På 3. semester skal du specialisere dig i enten Content Produktion eller User Interfaces (UI). <br> <b>Content Produktion</b><br>Du lærer, hvordan du ved hjælp af digitale løsninger kan skabe vedvarende konkurrencefordele for virksomheder.<br>Du får forståelse for målgruppeanalyse, webanalyse og marketingsværktøjer samt færdigheder inden for copywriting, brandfortælling og indholdsproduktion.<br><b>User Interfaces (UI)</b> <br>Du får grundlæggende indsigt i forskellige teknologier og frameworks med fokus på udvikling og optimering af arbejdsgange.<br>Du lærer at udvikle brugergrænseoverflader og deploye løsninger ved hjælp af diverse teknologier samt at forstå bagvedliggende datadrevne teknologier.",
  },
  {
    dropdown: "Undervisning",
    answer:
      "Under hele studiet arbejder du primært i teams og har løbende præsentationer både for holdet og klienter.<br>Undervisningen består af en stor del projektorienteret undervisning, hvor du arbejder med foto, video, design og programmering i teams og selvstændigt.<br><b>Tværfaglige projekter</b>Som studerende vil du arbejde med tværfaglige projekter, der trækker på elementer fra forskellige fag, og du vil skrive en del rapporter, hvor du skal argumenterer teoretisk for dine valg til løsning af givne problemstillinger.<br><b>Din tilgang som studerende</b><br>Som studerende er du selvkørende, og du spiller selv en vigtig rolle i at dygtiggøre dig undervejs på studiet – bl.a. gennem litteratursøgning, praktisk arbejde, projektpræsentationer og peer-feedback.<br>Størstedelen af litteraturen vil være på engelsk, da det også er branchens praksis at anvende engelske begreber.<br>Vi ser gerne, at du er nysgerrig på nye tendenser og ny teknologi.<br>På multimediedesigneruddannelsen taler vi ikke om lektier – du læser for din egen og din kommende arbejdsgivers skyld.<br><b>Programmer</b><br>Du får brug for adgang til en række af Adobes programmer til bl.a. redigering af billeder, video og lyd. Vi arbejder med den nyeste udgave af følgende programmer:<br><br><ul><li>Photoshop</li><li>InDesign</li><li>After effects</li><li>Premiere Pro</li><li>Illustrator</li><li>Lightroom Classic</li><li>Figma</li></ul><br>Du kan købe adgang til “Adobe Creative Cloud All Apps” via Adobes hjemmeside.<br> - <i><b>Adobes hjemmeside</b></i><br>Krav til computer på uddannelsen finder du på Adobes webside. Det er anbefalet at vælge en computer med Adobes anbefalede specifikationer. <br><i><b>- Se specifikationer </b></i>",
  },
  {
    dropdown: "Labs til rådighed",
    answer:
      "Uddannelsen råder over moderne lab-faciliteter som fx:<br><b>Medialab</b>, hvor du kan arbejde med greenscreen optagelser, foto, video og audio produktion, samt AR/VR/MR og Motion capture-teknologier. <br><b>Lydstudie</b>, hvor du kan arbejde med audio- og musikproduktioner, eksempelvis podcasts, speak og lign.<br><b>Neurolab</b>, hvor du kan brugerteste digitale og analoge brugergrænseflader og arbejde med forskellige biometriske værktøjer som fx Eyetracker og EEG. <br><b>Fablab</b>, hvor du kan arbejde med tryk, 3D-print og mock-ups.",
  },
  {
    dropdown: "Studiedokumenter",
    answer:
      "Se uddannelsens studieordning, semesterbeskrivelser og øvrige dokumenter.<br> <i><b>- Studiedokumenter på ucl.dk</b></i>",
  },
]);

const dropdown2 = ref([
  {
    dropdown: "Undervisning",
    semester: "1. semester",
    answer:
      "<b>Multimedieproduktion 1 (30 ECTS)</b><br>På 1. semester er undervisningen tilrettelagt som en blanding af individuelt arbejde, gruppeprojekter og real life-opgaver i samarbejde med virksomheder.<br>Her opbygger du et fagligt fundament og får en grundlæggende forståelse for arbejdet med digitale brugergrænseflader og digitalt indhold.",
  },
  {
    dropdown: "Undervisning",
    semester: "2. semester",
    answer:
      "<b>Multimedieproduktion 2 (30 ECTS)</b><br>På 2. semester arbejder du videre med at designe og programmere komplekse digitale løsninger med særligt fokus på brugergrænsefladen.<br>Du lærer om centrale metoder til udvikling og tests af brugeres oplevelser, således du kan sikre en god brugeroplevelse.<br>Du arbejder både individuelt og sammen med dine medstuderende i gruppeprojekter, hvor I løser udfordringer for en virksomhed.<br>I projekterne implementeres den teori, du har lært, og du bringer alle dine værktøjer i brug.",
  },
  {
    dropdown: "Undervisning",
    semester: "3. semester",
    answer:
      "<b>Valgfag (30 ECTS)</b><br>På 3. semester vælger du mellem de to specialiseringer<ul><li>Content Produktion</li><li>User Interfaces</li></ul>",
  },
  {
    dropdown: "Undervisning",
    semester: "4. semester",
    answer:
      "<b>Praktik (15 ECTS)</b><br>4. semester tilbringer du i et praktikforløb, hvor du får mulighed for at prøve, hvordan det er at være en del af en fysisk virksomhed.<br><b>Afsluttende eksamensprojekt (15 ECTS)</b><br>Herefter afslutter du uddannelsen og skriver din hovedopgave, som kan være i samarbejde med din praktikvirksomhed.",
  },
]);

function toggleDropdown(index) {
  openIndex.value = openIndex.value === index ? null : index;
}

function toggleDropdown2(index) {
  openIndex2.value = openIndex2.value === index ? null : index;
}

function isOpen(index) {
  return openIndex.value === index;
}

function isOpen2(index) {
  return openIndex2.value === index;
}
</script>

<template>
  <section id="uo-scroll">
    <h2>Uddannelsens opbygning</h2>
    <div class="buttom-divider">
      <div class="buttom-divider-width">
        <p>
          Uddannelsen til multimediedesigner varer 2 år og består af en
          fællesdel og en specialiseringsdel. Sidstnævnte byder på valgfag,
          praktik og hovedopgave.
        </p>
        <div class="item-wrap">
          <div
            class="dropdown-wrap_uo"
            v-for="(item, index) in dropdowns"
            :key="index"
          >
            <div class="dropdown_uo" @click="toggleDropdown(index)">
              <h4>{{ item.dropdown }}</h4>
              <img src="../assets/img/arrow-down.svg" alt="arrow" />
            </div>
            <div class="answer_uo" v-if="isOpen(index)">
              <p v-html="item.answer"></p>
            </div>
          </div>
        </div>
      </div>

      <div class="buttom-divider-width">
        <h3>Semesteroversigt</h3>
        <div class="oversigt_uo">
          <div class="buttom-divider-width flex_uo">
            <div class="box_uo box_uo_moerk"></div>
            <p>Praktik</p>
          </div>
          <div class="buttom-divider-width flex_uo">
            <div class="box_uo box_uo_lys"></div>
            <p>Undervisning</p>
          </div>
        </div>
        <div class="item-wrap">
          <div
            class="semester-wrap_uo"
            v-for="(item1, index) in dropdown2"
            :key="index"
          >
            <h4>{{ item1.semester }}</h4>
            <div class="semester-inner-wrap">
              <div class="semester_uo" @click="toggleDropdown2(index)">
                <h4>{{ item1.dropdown }}</h4>
              </div>
              <img src="../assets/img/arrow-down.svg" alt="arrow" />
            </div>
            <div class="semester-answer_uo" v-if="isOpen2(index)">
              <p v-html="item1.answer"></p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
