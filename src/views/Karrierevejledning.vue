<script setup>
import KVarrangementer from "@/components/KVarrangementer.vue";
import KVjobportalen from "@/components/KVjobportalen.vue";
import KVreviews from "@/components/KVreviews.vue";
import KVtjekliste from "@/components/KVtjekliste.vue";
import KVtilbud from "@/components/KVtilbud.vue";
import KVkontaktUCL from "@/components/KVkontaktUCL.vue";
import KVnavigation from "@/components/KVnavigation.vue";
import KVbookKarrierevejledning from "@/components/KVbookKarrierevejledning.vue";
import KVtop from "@/components/KVtop.vue";
import KVchatbot from "@/components/KVchatbot.vue";
</script>

<template>
  <KVtop />

  <div class="main-wrap">
    <KVnavigation />

    <div class="content-wrap">
      <KVtilbud />
      <KVbookKarrierevejledning />
      <KVtjekliste />
      <KVreviews />
      <KVjobportalen />
      <KVarrangementer />
      <KVkontaktUCL />
      <KVchatbot />
    </div>
  </div>
</template>
