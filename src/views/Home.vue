<template>
  <div class="home">
    <HeaderHijabKabul />
    <HeroHijabKabul />
    <WomenHijabKabul />
    <InstaHijabKabul />
    <PartnerHijabKabul />
    <FooterHijabKabul />
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from "@/components/HelloWorld.vue";
import HeaderHijabKabul from "@/components/HeaderHijabKabul.vue";
import HeroHijabKabul from "@/components/HeroHijabKabul.vue";
import WomenHijabKabul from "@/components/WomenHijabKabul.vue";
import InstaHijabKabul from "@/components/InstaHijabKabul.vue";
import PartnerHijabKabul from "@/components/PartnerHijabKabul.vue";
import FooterHijabKabul from "@/components/FooterHijabKabul.vue";

export default {
  name: "Home",
  components: {
    HeaderHijabKabul,
    HeroHijabKabul,
    WomenHijabKabul,
    InstaHijabKabul,
    PartnerHijabKabul,
    FooterHijabKabul,
  },
};
</script>
