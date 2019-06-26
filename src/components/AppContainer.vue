<template>
  <div class="app">
    <div class="container-fluid container">
      <div class="row body-container">
        <div class="col-8">
          <b-card>
            <Calculation />
            <Verplichtingen />
            <HuidigeWoning />
            <NieuweWoning />
            <HypotheekSamenstellen />
          </b-card>
        </div>
        <div class="col-4">
          <OutcomeCalculation />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Calculation from "@/components/Calculation.vue";
import OutcomeCalculation from "@/components/OutcomeCalculation.vue";
import Verplichtingen from "@/components/Verplichtingen.vue";
import HuidigeWoning from "@/components/HuidigeWoning.vue";
import NieuweWoning from "@/components/NieuweWoning.vue";
import HypotheekSamenstellen from "@/components/HypotheekSamenstellen.vue";

export default {
  name: "AppContainer",
  components: {
    Calculation,
    OutcomeCalculation,
    Verplichtingen,
    HuidigeWoning,
    NieuweWoning,
    HypotheekSamenstellen
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$imagePath: "~@tjip/emerald-global/scss/images/";
$iconsSystemPath: "~@tjip/emerald-icons/src/icons/system/";
$iconsProductPath: "~@tjip/emerald-icons/src/icons/product/";
@import "~@tjip/emerald-icons/src/scss/_product-icons.scss";
@import "@tjip/emerald-global/scss/_emerald_variables.scss";
@import "@tjip/emerald-global/scss/_emerald_icons.scss";

.app {
  margin-top: -40px;
}

h3 {
  margin-bottom: 0;
}

.card {
  margin-bottom: 40px;
  &:hover {
    cursor: pointer;
    box-shadow: $em-box-shadow-well;
  }
  &-header {
    font-family: $headings-font-family;
    color: $g-300;
    background-color: $white;
    border-bottom: 0;
  }

  &-body {
    padding: 0;
  }
}
</style>
