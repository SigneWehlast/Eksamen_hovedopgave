<template>
  <section id="kontaktka">
    <h2>Kontakt Karrievejledning</h2>
    <div class="contact">
      <div class="contact-inner">
        <img src="../assets/img/dennis.png" alt="" />
        <h3>Dennis Færch Broch</h3>
        <p>Dimittend- og karrierekonsulent</p>
        <b> <p class="paragraf-kontakt-os">Kontakt os</p> </b>
      </div>
      <div class="contact-inner">
        <img src="../assets/img/morten.png" alt="" />
        <h3>Morten Jung Lassen</h3>
        <p>Karrierevejleder</p>
        <b> <p class="paragraf-kontakt-os">Kontakt os</p> </b>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  display: flex;
  justify-content: space-evenly;
  background-color: #f8ccc4;
  margin: 0 auto;
  padding: 5%;
}

.contact img {
  height: 200px;
  width: 200px;
}

.contact-inner {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.paragraf-kontakt-os {
  border-bottom: 2px solid #000;
  border-bottom-style: dotted;
  cursor: pointer;
}

@media screen and (max-width: 700px) {
  .contact img {
    height: 150px;
    width: 150px;
  }

  .contact {
    display: flex;
    flex-direction: column;
  }

  .contact-inner {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }
}
</style>
