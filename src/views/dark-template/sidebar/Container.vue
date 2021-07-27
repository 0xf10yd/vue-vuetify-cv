<template>
  <v-card
    color="grey darken-4"
    dark
  >
    <avatar />
    <v-card-text>
      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: '0xf10yd@protonmail.com',
            },
            {
              name: 'Website',
              icon: 'mdi-web',
              text: '0xf10yd.github.io',
            },
            {
              name: 'Phone',
              icon: 'mdi-phone',
              text: '+201093912694',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/0xf10yd',
              link: 'https://github.com/0xf10yd',
            },
            {
              icon: 'mdi-linkedin-box',
              text: 'linkedin.com/in/0xf10yd',
              link: 'https://linkedin.com/in/0xf10yd',
            },
            {
              icon: 'mdi-android-debug-bridge',
              text: 'hackerone.com/bluething',
              link: 'https://hackerone.com/bluething',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            {
              icon: 'mdi-chess-knight',
              text: 'Chess',
            },
            {
              icon: 'mdi-biohazard',
              text: 'Pentesting',
            },
            {
              icon: 'mdi-teach',
              text: 'Mentorship',
            },
            {
              icon: 'mdi-karate',
              text: 'Krav Maga',
            },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            },
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text : 'English',
              value: 98,
            },
            {
              text : 'Arabic',
              value: 99,
            },
            {
              text : 'French',
              value: 90,
            },
            {
              text : 'Russian',
              value: 78,
            },
            {
              text : 'Hebrew',
              value: 65,
            },
            {
              text : 'Mandarin',
              value: 35,
            },
            {
              text : 'Italian',
              value: 30,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
