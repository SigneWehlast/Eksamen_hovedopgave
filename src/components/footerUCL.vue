<template>
  <footer>
    <div class="footer-main">
      <div class="footer-1">
        <ul>
          <li>Studieservice</li>
          <li>Events</li>
          <li>Studieliv</li>
        </ul>
      </div>
      <div class="footer-2">
        <ul>
          <li>Biblotek</li>
          <li>Tilgængelighedserklæring</li>
        </ul>
      </div>
      <div class="footer-3">
        <ul>
          <li>mitUCL.dk er et website for studerende på UCL.</li>
          <br />
          <li>
            UCL Erhvervsakademi og Professionshøjskole udbyder 43 uddannelser i
            Odense, Svendborg, Vejle, Fredericia og Jelling. Som studerende
            kommer du tæt på virkeligheden og vil i fremtiden bidrage til
            bæredygtig vækst, velfærd og løsninger, der gør en forskel.
          </li>
        </ul>
        <div>
          <video class="footer-video" width="100%" controls>
            <source
              src="../assets/Video/mitucl.dk.mp4" type="video/mp4">
          </video>
        </div>
      </div>
    </div>

    <div class="footer-icons">
      <img src="../assets/img/facebook.icon.svg" alt="" />
      <img src="../assets/img/instagram-icon.svg" alt="" />
      <img src="../assets/img/twitter-icon.svg" alt="" />
      <img src="../assets/img/linkedin-icon.svg" alt="" />
    </div>

    <div class="footer-bottom-line">
      <p>© 2024 UCL Erhvervsakademi og Professionshøjskole</p>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background-color: #1a444d;
}
.footer-main {
  color: #fff;
  display: flex;
  flex-direction: row;
  padding-left: 10%;
  padding-right: 10%;
  padding-top: 10%;
}

.footer-1 {
  width: 25%;
}

.footer-2 {
  width: 25%;
}

.footer-3 {
  width: 50%;
}

ul {
  list-style: none;
  padding: 0;
}

.footer-image img {
  display: flex;
  width: 400px;
}

.footer-icons {
  display: flex;
  flex-direction: row;
  gap: 10px;
  padding-left: 15%;
  padding-bottom: 10%;
  padding-top: 5%;
}

.footer-icons img {
  height: 15px;
  width: 15px;
}

.footer-bottom-line {
  background-color: #122f36;
  color: #fff;
  font-size: 20px;
  text-align: center;
  padding: 1%;
  border-top: 1px solid #707070;
}

.footer-bottom-line p {
  color: #fff;
}

@media screen and (max-width: 1100px) {
  .footer-main {
    color: #fff;
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 1000px;
    font-size: 20px;
    line-height: 4.8rem;
  }

  .footer-1 {
    width: 100%;
  }

  .footer-2 {
    width: 100%;
  }

  .footer-3 {
    width: 100%;
  }

  .footer-icons img {
    height: 30px;
    width: 30px;
  }

  .footer-image img {
    display: flex;
    width: 100%;
  }

  .footer-1 .footer-2 li {
    font-size: 30px;
  }

  .footer-video {
    width: 100%;
    height: 100%;
  }
}
</style>
