<template>
  <div class="text-md-center avatar">
    <v-avatar
      class="image"
      color="grey"
      size="165"
    >
      <img
        :src="publicPath('/img/avatar.jpg')"
        alt="Muhammad Ahmad"
      >
    </v-avatar>
    <div class="text-sm-center mb-4 mt-3">
      <h1>
        <span class="font-weight-black text--lighten-3">Muhammad</span>
        <br>
        <span class="font-weight-light text--lighten-3">Ahmad</span>
      </h1>
      <v-row class="align-content">
        <v-icon>mdi-map-marker</v-icon>
        <p>Port Said, Egypt</p>
      </v-row>
      <v-row class="align-content">
        <v-icon>mdi-calendar-week</v-icon>
        <p>21th August 2002</p>
      </v-row>
      <br>
      <h3 class="text-center font-weight-medium text-uppercase font-weight-black">
        About or fun facts
      </h3>
      <p class="text-center font-weight-light">
        I'm an entitled chess player, a ployglot, a top notch SWE and somehow narcissistic. Sometimes I find myself in the middle of an existential dreed, but I find peace eventually
      </p>
    </div>
  </div>
</template>

<script>
export default { name: 'Avatar' }
</script>

<style scoped>
.avatar{
  display: block;
  top: 0px;
  left: 0px;
  height: 540px;
  background: transparent linear-gradient(210deg, #3F68EA 20%, #252731 80%) 0% 0% no-repeat padding-box;
  box-shadow: 0px 0px 35px #141A1F29;
  opacity: 1;
  }
.image{
  margin-top: 20px;
}
.material-icons, .icon-text {
  vertical-align: middle;
}
</style>
