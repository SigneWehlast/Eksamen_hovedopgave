<script></script>

<template>
  <section id="tjekliste">
    <h2 class="italic">Karriere tjekliste</h2>

    <div class="flex-overordnet">
      <div class="flex-tjekliste">
        <div class="semester-opdeling">
          <p class="italic">1. semester</p>

          <div class="checkbox-class">
            <img
              class="check-img"
              src="../assets/img/check.svg"
              alt="checkmark"
            />
            <p>LinkedIn profil</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Praktiksøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>CV og ansøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Jobsøgningsstrategi</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Kompetenceafklaring</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Praktiksamtale</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Jobsamtalen</p>
          </div>
        </div>

        <div class="semester-opdeling">
          <p class="italic">2. semester</p>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>LinkedIn profil</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Praktiksøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>CV og ansøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Jobsøgningsstrategi</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Kompetenceafklaring</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Praktiksamtale</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Jobsamtalen</p>
          </div>
        </div>
      </div>

      <div class="flex-tjekliste">
        <div class="semester-opdeling">
          <p class="italic">3. semester</p>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>LinkedIn profil</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Praktiksøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>CV og ansøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Jobsøgningsstrategi</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Kompetenceafklaring</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Praktiksamtale</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/cross.svg" alt="cross" />
            <p>Jobsamtalen</p>
          </div>
        </div>

        <div class="semester-opdeling">
          <p class="italic">4. semester</p>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>LinkedIn profil</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Praktiksøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>CV og ansøgning</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Jobsøgningsstrategi</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Kompetenceafklaring</p>
          </div>

          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Praktiksamtale</p>
          </div>
          <div class="checkbox-class">
            <img class="check-img" src="../assets/img/check.svg" alt="check" />
            <p>Jobsamtalen</p>
          </div>
        </div>
      </div>
    </div>

    <div>
      <a href="/src/assets/PDF/Karrieretjekliste.pdf" target="_blank" class="download-file">Download karriere tjeklisten som PDF</a>
    </div>

    <button class="btn-yellow btn-guide-tjekliste">
      Guide: Bliv klar til din karriere gennem hele din uddannelse
    </button>
  </section>
</template>

<style scoped>

.download-file {
  position: relative;
  top: 20px;
  color: #1a424b;
}

.btn-guide-tjekliste {
  position: relative;
  top: 20px;
}

@media screen and (max-width: 700px) {
  .btn-yellow {
    text-align: left;
    padding: 10px;
    line-height: 20px;
  }

  .flex-tjekliste {
    gap: 40px;
  }

  .flex-overordnet {
    gap: 20px;
  }
}
</style>
