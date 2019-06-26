<template>
  <div class="popup-verplichtingen">
    <b-button v-b-modal.modal-1>Specificeer</b-button>

    <b-modal id="modal-1" title="Verplichtingen">
      <div role="tablist">
        <b-card no-body class="mb-1">
          <b-card-header
            header-tag="header"
            class="checkbox-accordion"
            role="tab"
          >
            <b-button
              href="#"
              v-b-toggle.studieschuld
              variant="checkbox-accordion"
              >Studieschuld</b-button
            >
          </b-card-header>
          <b-collapse
            id="studieschuld"
            accordion="my-accordion"
            role="tabpanel"
          >
            <b-card-body>
              <b-card-text>Studieschuld komt hier info</b-card-text>
              <b-card-text>{{ text }}</b-card-text>
            </b-card-body>
          </b-collapse>
        </b-card>

        <b-card no-body class="mb-1">
          <b-card-header
            header-tag="header"
            class="checkbox-accordion"
            role="tab"
          >
            <b-button
              block
              href="#"
              v-b-toggle.partneralimentatie
              variant="checkbox-accordion"
              >Partneralimentatie</b-button
            >
          </b-card-header>
          <b-collapse
            id="partneralimentatie"
            accordion="my-accordion"
            role="tabpanel"
          >
            <b-card-body>
              <b-card-text>Partneralimentatie komt hier info</b-card-text>
            </b-card-body>
          </b-collapse>
        </b-card>

        <b-card no-body class="mb-1">
          <b-card-header
            header-tag="header"
            class="checkbox-accordion"
            role="tab"
          >
            <b-button
              block
              href="#"
              v-b-toggle.overige-leningen
              variant="checkbox-accordion"
              >Overige leningen</b-button
            >
          </b-card-header>
          <b-collapse
            id="overige-leningen"
            accordion="my-accordion"
            role="tabpanel"
          >
            <b-card-body>
              <b-card-text>Overige leningen komt hier info</b-card-text>
            </b-card-body>
          </b-collapse>
        </b-card>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "VerplichtingenPopup"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$imagePath: "~@tjip/emerald-global/scss/images/";
$iconsSystemPath: "~@tjip/emerald-icons/src/icons/system/";
$iconsProductPath: "~@tjip/emerald-icons/src/icons/product/";
@import "~@tjip/emerald-icons/src/scss/_product-icons.scss";
@import "~@tjip/emerald-icons/src/scss/_system-icons.scss";
@import "@tjip/emerald-global/scss/_emerald_variables.scss";
@import "@tjip/emerald-global/scss/_emerald_icons.scss";

.btn-secondary {
  height: 100%;
  background-color: $g-50;
  color: $g-300;
  border: 1px solid transparent;
  box-shadow: inset 0 0 0 1px $gm-75;
  font-size: 16px;
  border-radius: 0.125rem;
  border-top-right-radius: 0.125rem;
  border-bottom-right-radius: 0.125rem;
  justify-content: center;
  &:not(:first-child) {
    margin-left: 5px;
    border-top-left-radius: 0.125rem;
    border-bottom-left-radius: 0.125rem;
  }
  &:hover,
  &:not(:disabled):not(.disabled).active,
  &:not(:disabled):not(.disabled):active {
    background-color: $g-50;
    color: $g-300;
    border: 1px solid $g-400;
  }
}

.checkbox {
  &-accordion {
    padding: 0;
    border: 0px;
    background-color: transparent;
  }
}

.card {
  border: 0;
}

.btn {
  &-checkbox {
    &-accordion {
      transition: none;
      text-align: left;
      padding-left: 2rem;
      position: relative;
      &:before {
        content: "";
        width: 25px;
        height: 25px;
        position: absolute;
        left: 0;
        background-image: url(#{$iconsSystemPath}sy-form-checkbox.svg);
        background-size: cover;
      }
      &:after {
        content: "";
        width: 20px;
        height: 20px;
        position: absolute;
        left: 0;
        background-image: url(#{$iconsSystemPath}sy-form-valid.svg);
        opacity: 0;
      }
      &[aria-expanded="true"] {
        &:after {
          opacity: 1;
        }
      }
      &:focus {
        box-shadow: none;
      }
    }
  }
}
</style>
