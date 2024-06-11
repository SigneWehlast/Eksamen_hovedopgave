<script setup>
import { onMounted, ref } from "vue";

const arrangementer = ref([]);
const error = ref(null);

onMounted(() => {
  getArrangementerSection();
});

const getArrangementerSection = () => {
  fetch(
    "https://hovedopgave-f875e-default-rtdb.firebaseio.com/arragementer.json",
    {
      method: "GET",
    }
  )
    .then((res) => res.json())
    .then((res) => {
      console.log(res);
      arrangementer.value = res;
    })
    .catch((err) => {
      console.log(err);
      error.value = "Kunne ikke hente data";
    });
};
</script>

<template>
  <section id="arrang">
    <h2>Arrangementer</h2>
    <p>
      Se karrierevejlednings hos UCL's kommende arrangementer, for din som
      studerende og bliv klogere på fremtidsmuligheder og din karriere
    </p>
    <div class="arrangementer_container">
      <div
        v-for="(arrangementer, index) in arrangementer"
        :key="index"
        class="arrangementer_box"
      >
        <div
          class="arrangementer_image"
          :style="{ backgroundImage: `url(${arrangementer.image})` }"
        ></div>
        <div>
          <p class="arrangementer_dato">{{ arrangementer.dato }}</p>
        </div>
        <div>
          <p class="arrangementer_titel">{{ arrangementer.titel }}</p>
        </div>
        <div>
          <p class="arrangementer_location">{{ arrangementer.location }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.arrangementer_image {
  width: 100%;
  height: 200px;
  background-size: cover;
  background-position: center;
}

.arrangementer_box {
  width: 50%;
}

#arrangementer_img {
  max-width: 450px;
  height: auto;
}

.arrangementer_container {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
  gap: 40px;
}

.arrangementer_dato {
  font-weight: bold;
}

@media screen and (max-width: 700px) {
  .arrangementer_container {
    gap: 20px;
    display: flex;
    flex-direction: column;
  }

  .arrangementer_box {
    width: 100%;
  }
}
</style>
