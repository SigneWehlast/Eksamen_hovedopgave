<script setup>
import { ref } from "vue";
import forsideNavigation from "@/components/forsideNavigation.vue";
import Fstudiestart from "@/components/Fstudiestart.vue";
import FUdannelsensOpbygning from "@/components/FUdannelsensOpbygning.vue";
import Fpraktik from "@/components/Fpraktik.vue";
import FInternationalemuligheder from "@/components/FInternationalemuligheder.vue";
import FKVmuligheder from "@/components/FKVmuligheder.vue";
import FGenveje from "@/components/FGenveje.vue";
import FEvent from "@/components/FEvent.vue";
import FAi from "@/components/FAi.vue";
import Fvidereuddannelse from "@/components/Fvidereuddannelse.vue";
</script>

<template>
  <div class="main-wrap">
    <forsideNavigation />

    <div class="content-wrap">
      <Fstudiestart />
      <FUdannelsensOpbygning />
      <FAi />
      <Fpraktik />
      <FKVmuligheder />
      <Fvidereuddannelse />
      <FInternationalemuligheder />
      <FGenveje />
      <FEvent />
    </div>
  </div>
</template>
