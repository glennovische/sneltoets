<template>
  <div class="calc">
    <b-card header="Uw berekening" header-tag="h3">
      <div class="row">
        <label class="col-6">Wat je maximaal kan lenen</label>
        <div class="col-6 text-right">€0,00</div>
      </div>
      <div class="row border-bottom">
        <label class="col-6">Maximale bruto maandlasten</label>
        <div class="col-6 text-right">€0,00</div>
      </div>

      <div class="row">
        <label class="col-6">
          <strong>Wat je maximaal kan lenen</strong>
        </label>
        <div class="col-6 text-right">€0,00</div>
      </div>
      <div class="row">
        <label class="col-6">Bruto maandlasten</label>
        <div class="col-6 text-right">€0,00</div>
      </div>
      <div class="row">
        <label class="col-6">Netto maandlasten</label>
        <div class="col-6 text-right">€0,00</div>
      </div>

      <h3 class="mt-4">Uitgangspunten</h3>
      <div class="row mb-4">
        <label class="col-6">Huisbankkorting</label>
        <div class="col-6">
          <b-form-group>
            <b-form-radio-group
              class="abn-radio"
              id="huisbankkorting"
              buttons
              size="lg"
              name="radios-btn-default"
            >
              <b-form-radio name="some-radios" value="Ja">Ja</b-form-radio>
              <b-form-radio name="some-radios" value="Nee">Nee</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </div>
      </div>
      <div class="row mb-4">
        <label class="col-6">Duurzaamheids korting</label>
        <div class="col-6">
          <b-form-group>
            <b-form-radio-group
              class="abn-radio"
              id="duurzaamheidskorting"
              buttons
              size="lg"
              name="radios-btn-default"
            >
              <b-form-radio name="some-radios" value="Ja">Ja</b-form-radio>
              <b-form-radio name="some-radios" value="Nee">Nee</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </div>
      </div>
      <div class="row mb-4">
        <label class="col-6">NHG</label>
        <div class="col-6">
          <b-form-group>
            <b-form-radio-group
              class="abn-radio"
              id="nhg"
              buttons
              size="lg"
              name="radios-btn-default"
            >
              <b-form-radio name="some-radios" value="Ja">Ja</b-form-radio>
              <b-form-radio name="some-radios" value="Nee">Nee</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </div>
      </div>
      <div class="row mb-4">
        <label class="col-6">Soort hypotheek</label>
        <div class="col-6">
          <b-form-group>
            <b-form-radio-group
              class="abn-radio"
              id="soort_hypotheek"
              buttons
              size="lg"
              name="radios-btn-default"
            >
              <b-form-radio name="some-radios" value="Ja">Ja</b-form-radio>
              <b-form-radio name="some-radios" value="Nee">Nee</b-form-radio>
            </b-form-radio-group>
          </b-form-group>
        </div>
      </div>
      <b-button block variant="warning" href="#">Start hypotheekaanvraag</b-button>
      <b-button block variant="info" href="#">
        <div class="em-icon em-icon-size-4 sy-tools-star"></div>Print dit overzicht
      </b-button>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "OutcomeCalculation",
  props: ["maxcalc"],
  data() {
    return {
      maxCalc: ""
    };
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
@import "../assets/scss/index.scss";

.app {
  margin-top: -40px;
}

h3 {
  margin-bottom: 0;
}

label {
  padding-left: $spacer;
}

.card {
  border: 0;
  &-header {
    height: 72px;
    font-family: $headings-font-family;
    color: $white;
    background-color: $g-400;
    border-bottom: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  &-body {
    border: 1px solid rgba(0, 0, 0, 0.125);
  }
}

.em {
  &-icon {
    &-size {
      &-4 {
        width: 18px;
        height: 18px;
        background-size: contain;
      }
    }
  }
}
</style>
