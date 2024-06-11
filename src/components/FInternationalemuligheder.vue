<script setup></script>

<template>
  <section id="imScroll">
    <h2>Internationale muligheder</h2>

    <div class="buttom-divider" id="none">
      <div class="buttom-divider-width international-img"></div>
      <div class="buttom-divider-width">
        <h3>3 muligheder for at rejse ud</h3>
        <p>- En praktikperiode i udlandet</p>
        <p>- Et udlandsophold i forbindelse med et valgfag</p>
        <p>- Et engelsksprogede forløb på UCL</p>
        <div class="btn-green">
          <p>Rejs ud under studie</p>
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
    <h3>International vejledning</h3>
    <div class="buttom-divider">
      <div class="buttom-divider-width">
        <div class="blue-card">
          <h3>International koordinator</h3>
          <div class="card-inner">
            <img
              class="profile-img"
              src="../assets/img/lars.png"
              alt="Prkatik koordinator profil billede"
            />
            <div class="koordinator-info">
              <h4>Lars Christian Bojen Nielsen</h4>
              <p>International koordinator</p>
              <div class="list">
                <img src="../assets/img/phone-icon.svg" alt="" />
                <p>65 43 48 01</p>
              </div>
              <div class="list">
                <img src="../assets/img/mail-icon.svg" alt="" />
                <p>lcbn@ucl.dk</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="buttom-divider-width">
        <h3>Internationalt team</h3>
        <p>
          Kontakt Internationalt team, hvis du har behov for råd og vejledning
          om praktiske og administrative spørgsmål som f.eks. ansøgning og
          stipendier.<br /><br />
          Du kontakter Internationalt team ved at oprette en sag via
          service.ucl.dk, hvor du vælger Studieservice => Mit Studieforløb =>
          Udlandsophold.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.international-img {
  background-image: url("../assets/img/internationalemuligheder.png");
  background-size: cover;
  height: 250px;
}

.internationalemuligheder-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.arrow {
  fill: #fae76a;
  display: flex;
  align-items: center;
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

.blue-card {
  background-color: #daeced;
  padding: 20px;
}
</style>
