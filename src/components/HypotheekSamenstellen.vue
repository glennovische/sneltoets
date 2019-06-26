<template>
  <div class="mortgage-build">
    <b-card-header no-body v-b-toggle.hypotheek-samenstellen class="row">
      <div class="em-icon em-icon-size-8 pr-tools-sliders"></div>
      <h3 class="d-flex align-self-center">Hypotheek Samenstellen</h3>
      <div class="em-icon em-icon-size-8 toggle sy-arrow-chevron-up"></div>
    </b-card-header>
    <b-collapse id="hypotheek-samenstellen" visible>
      <b-card-body>
        <div class="row mb-4">
          <label for class="col-4">Toetsinkomen</label>
          <div class="col-4">
            <b-input-group size="lg" prepend="€">
              <b-form-input v-model="maxCalc"></b-form-input>
            </b-input-group>
            <div class="mt-2">Value: {{ maxCalc }}</div>
          </div>
        </div>

        <div class="row mb-4">
          <label for class="col-4">Bent u momenteel AOW-gerechtigd?</label>
          <div class="col-4">
            <b-form-group>
              <b-form-radio-group
                class="abn-radio"
                id="aow"
                buttons
                size="lg"
                name="radios-btn-default"
              >
                <b-form-radio name="aow-radio" value="Ja">Ja</b-form-radio>
                <b-form-radio name="aow-radios" value="Nee">Nee</b-form-radio>
              </b-form-radio-group>
            </b-form-group>
          </div>
        </div>

        <div class="row mb-4">
          <label for class="col-4">Heeft u een partner?</label>
          <div class="col-4">
            <b-form-group>
              <b-form-radio-group
                class="abn-radio"
                id="partner"
                buttons
                size="lg"
                name="radios-btn-default"
              >
                <b-form-radio v-b-toggle.partner name="partner-radios" value="Ja">Ja</b-form-radio>
                <b-form-radio name="partner-radios" value="Nee">Nee</b-form-radio>
              </b-form-radio-group>
            </b-form-group>
          </div>
        </div>

        <b-collapse id="partner">
          <div class="row mb-4">
            <label for class="col-4">Toetsinkomen</label>
            <div class="col-4">
              <b-input-group size="lg" prepend="€">
                <b-form-input></b-form-input>
              </b-input-group>
              <b-form-checkbox
                id="checkbox-1"
                name="checkbox-1"
                value="accepted"
                unchecked-value="not_accepted"
              >Belastingplichting in het buitenland</b-form-checkbox>
            </div>
          </div>

          <div class="row mb-4">
            <label for class="col-4">Bent u momenteel AOW-gerechtigd?</label>
            <div class="col-4">
              <b-form-group>
                <b-form-radio-group
                  class="abn-radio"
                  id="btn-radios-1"
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
        </b-collapse>
      </b-card-body>
    </b-collapse>
  </div>
</template>

<script>
export default {
  name: "HypotheekSamenstellen",
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
@import "~@tjip/emerald-icons/src/scss/_system-icons.scss";
@import "@tjip/emerald-global/scss/_emerald_variables.scss";
@import "@tjip/emerald-global/scss/_emerald_icons.scss";

.collapsed > .when-opened,
:not(.collapsed) > .when-closed {
  display: none;
}

.app {
  margin-top: -40px;
}

h3 {
  margin-bottom: 0;
}

.card {
  &:hover {
    cursor: pointer;
    box-shadow: $em-box-shadow-well;
  }
  &-header {
    font-family: $headings-font-family;
    color: $g-300;
    background-color: $white;
    border-bottom: 0;
    padding: 0;
    margin: 0 15px;
    position: relative;
    &:before {
      content: "";
      border-top: 1px solid #dee2e6;
      position: absolute;
      top: 0;
      left: -15px;
      width: calc(100% + 30px);
    }
    &[aria-expanded="false"] {
      > .toggle {
        transform: rotate(180deg);
      }
    }
    &:first-child {
      border-radius: 0;
    }
    > .toggle {
      position: absolute;
      background-size: contain;
      position: absolute;
      right: 1rem;
      width: 1.5rem;
      height: 1.5rem;
      margin: 1.3rem 1rem;
      right: 0.25rem;
    }
  }
  &-body {
    padding: 0.75rem 1.25rem;
  }
}

.em {
  &-icon {
    &-size {
      &-8 {
        width: 64px;
        height: 64px;
        background-size: contain;
      }
    }
  }
}

.input {
  &-group {
    &-text {
      background-color: $white;
    }
  }
}
.form {
  &-control {
    text-align: right;
    border-left: 0;
    &:focus {
      border-color: #ced4da;
      box-shadow: none;
    }
  }
}

.custom {
  &-control {
    &-label {
      &::before {
        width: 100%;
        left: 0;
        border-radius: 0.125rem;
      }
    }
  }

  &-radio {
    padding-left: 0;
    display: inline-block;
    width: 50%;
    .custom {
      &-control {
        &-label {
          display: none !important;
          &:before {
            border-radius: 0.125rem !important;
          }
        }

        &-input {
          opacity: 1;
        }
      }
    }
  }
}

.abn {
  &-radio {
    width: 100%;
    .btn-secondary {
      width: 50%;
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
      &:not(:disabled):not(.disabled).active,
      &:not(:disabled):not(.disabled):active {
        background-color: $g-50;
        color: $g-300;
        border: 1px solid $g-400;
      }
    }
  }
}
</style>
