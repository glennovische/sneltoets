<template>
  <header>
    <div class="p-0 em-header-menu app-header">
      <div class="container-fluid d-flex heigt-max container">
        <h2 class="align-self-center">Maximale hypotheek berekenen</h2>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$imagePath: "~@tjip/emerald-global/scss/images/";
$iconsSystemPath: "@tjip/emerald-icons/src/icons/system/";
$iconsProductPath: "@tjip/emerald-icons/src/icons/product/";
@import "@tjip/emerald-global/scss/_emerald_variables.scss";

h2 {
  color: $white;
}

.app {
  &-header {
    width: 100%;
    height: 160px;
    background-size: auto, 100% 160px;
    background-image: url("../../assets/svg/em-header-gradient.svg"),
      linear-gradient(-135deg, $g-100 0, $g-200 100%);
    background-repeat: no-repeat;
    background-position: top;
  }
}

.heigt {
  &-max {
    height: 100%;
  }
}
</style>
