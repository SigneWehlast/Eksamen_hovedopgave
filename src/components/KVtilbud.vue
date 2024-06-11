<template>
  <section id="hkvt">
    <div class="shortcut-wrap">
      <h2>Hvad kan vi tilbyde</h2>
      <p>
        UCL's karrierevejledning kan give dig råd og vejledning i alt omkring
        din karriere igennem hele studiet. Her kan du dykke ned i, hvad de kan
        tilbyde dig.
      </p>
      <div class="item-wrap">
        <div class="dropdown-wrap" v-for="(item, index) in dropdowns">
          <div class="dropdown" @click="toggleDropdown(index)">
            <p>{{ item.dropdown }}</p>
            <img src="../assets/img/arrow-down.svg" alt="arrow" />
          </div>
          <div class="answer" v-if="openIndex === index">
            <p>{{ item.answer }}</p>
          </div>
        </div>
      </div>

      <button class="btn-yellow">
        Guide: Bliv klar til din karriere gennem hele din uddannelse
      </button>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const openIndex = ref(null);

const dropdowns = ref([
  {
    dropdown: "En-til-en vejledning",
    answer:
      "I en en-til-en vejledning med karrierevejledningen, kommer du til en vejledning enten fysisk eller online med en af de to vejledere. Til vejledningen kan du stille spørgsmål til alt inden for praktik og karriere, hertil kan du få feedback på din ansøgning, dit CV eller få en snak om dine bekymringer eller forventninger til din praktik. Du kan blandt andet også få vejledning omkring din fremtid inden for din uddannelse. Du kan booke en tid til vejledning i kalenderen nedenfor.",
  },
  {
    dropdown: "Vejledning på klassen/hold",
    answer:
      "Et af karriervejledningens tilbud er, at undervisere på UCL kan booke karrierevejledningen til at komme ud på de forskellige klasser/hold og holde oplæg omkring praktik og karriere. Dette sker ofte i forbindelse med praktiksøgningen eller i slutningen af uddannelsen, når de studerende skal ud og finde arbejde.",
  },
  {
    dropdown: "Karrierevejledning i grupper",
    answer:
      "Til en karrierevejledningen i grupper kan dig og din studiegruppe komme til vejledning enten fysisk eller online sammen med en af karrierevejlederne. Her kan i sammen stille spørgsmål til alt inden for praktik og karriere, og sammen få svar på de spørgsmål, som i brænder inde med. Dette kan blandt andet være jeres fremtidsmuligheder med den uddannelse i går på.",
  },
  {
    dropdown: "CV-tjek",
    answer:
      "På både UCL Boulevarden og UCL Seebladsgade er der en gang i måneden CV-tjek. Her kan du få feedback på dit CV eller din ansøgning. Når der er CV-tjek bliver det meldt ud på karrierevejledningens Facebookside.",
  },
  {
    dropdown: "Digitale guides",
    answer:
      "Hvis du er mere til at finde svarene selv, så har karrierevejledningen udarbejdet flere online guides til alt inden for praktik, praktiksøgning og karriere. Disse guides kan du finde på knappen nedenunder.",
  },
]);

function toggleDropdown(index) {
  openIndex.value = openIndex.value === index ? null : index;
}
</script>

<style scoped>
p {
  font-size: 18px;
}
.dropdown-wrap {
  border: solid 2px #cae4e3;
  margin-bottom: 20px;
  margin-top: 20px;
  cursor: pointer;
}

.dropdown-wrap:hover {
  background-color: #e2f1ee;
}

.dropdown {
  display: flex;
  justify-content: space-between;
  padding: 25px;
}

.answer {
  padding: 25px;
}

@media screen and (max-width: 700px) {
  .btn-yellow {
    text-align: left;
    padding: 10px;
    line-height: 20px;
  }
}
</style>
