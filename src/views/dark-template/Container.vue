<template>
  <v-app id="dark-template">
    <v-content>
      <v-container
        fluid
        fill-height
      >
        <v-layout
          align-center
          justify-center
        >
          <v-flex
            md10
            sm12
          >
            <v-layout wrap>
              <v-flex
                md4
              >
                <sidebar-container class="fill-height" />
              </v-flex>
              <v-flex
                md8
              >
                <content-container class="fill-height" />
              </v-flex>
            </v-layout>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import SidebarContainer from '@/views/dark-template/sidebar/Container'
import ContentContainer from '@/views/dark-template/content/Container'
export default {
  name      : 'DarkTemplateContainer',
  components: {
    ContentContainer,
    SidebarContainer,
  },
}
</script>

<style scoped>
#dark-template {
  height: 100%;
  background: -webkit-linear-gradient(to left, #66668d, #4389a2);
  background: linear-gradient(to left, #66668d, #4389a2);
  background-size: cover;
}
</style>
