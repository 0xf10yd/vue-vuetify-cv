<template>
  <v-card
    color="blue-grey darken-4"
    dark
  >
    <v-card-text>
      <content-section
        v-if="experience"
        title="Experience"
      >
        <v-layout
          v-for="(experience, i) in experience"
          :key="i"
          color="263238"
        >
          <v-flex md4>
            {{ experience.from }} - {{ experience.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="experience.title">{{ experience.title }}</strong>
            <div v-if="experience.location">
              <i>{{ experience.location }}</i>
            </div>
            <div v-if="experience.description">
              {{ experience.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div>
                  <h3 class="font-weight-black text-center text-uppercase">
                    {{ skill.title }}
                  </h3>
                </div>
                <v-progress-linear
                  class="progress"
                  height="12"
                  :value="skill.value"
                  style="background: transparent linear-gradient(90deg, #4040E3 0%, #3EDAFF 100%) 10% 12% no-repeat padding-box; border-radius: 30px;"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
    <v-container style="max-width: 600px;">
      <v-timeline
        dense
        clipped
      >
        <v-timeline-item
          fill-dot
          class="white--text mb-12"
          color="orange"
          large
        >
          <template v-slot:icon>
            <span>JL</span>
          </template>
          <v-text-field
            v-model="input"
            hide-details
            flat
            label="Leave a comment..."
            solo
            @keydown.enter="comment"
          >
            <template v-slot:append>
              <v-btn
                class="mx-0"
                depressed
                @click="comment"
              >
                Post
              </v-btn>
            </template>
          </v-text-field>
        </v-timeline-item>

        <v-slide-x-transition
          group
        >
          <v-timeline-item
            v-for="event in timeline"
            :key="event.id"
            class="mb-4"
            color="pink"
            small
          >
            <v-row justify="space-between">
              <v-col
                cols="7"
                v-text="event.text"
              />
              <v-col
                class="text-right"
                cols="5"
                v-text="event.time"
              />
            </v-row>
          </v-timeline-item>
        </v-slide-x-transition>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>Now, kindly apperciate the effort because it felt so real :)</span>
        </v-timeline-item>

        <v-timeline-item
          class="mb-4"
          color="grey"
          icon-color="grey lighten-2"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              Did some static analysis, tried to find anything buggy, checked how responsive the app is and compared performance with the other builds.
            </v-col>
          </v-row>
        </v-timeline-item>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>Finally</span>
        </v-timeline-item>

        <v-timeline-item
          class="mb-4"
          color="grey"
          icon-color="grey lighten-2"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              I made the best out of the Template I recieved, though I could've built a clone but I thought of going creative fot a bit "didn't go hard on it"
            </v-col>
          </v-row>
        </v-timeline-item>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>I lost count</span>
        </v-timeline-item>

        <v-timeline-item
          class="mb-4"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              <v-chip
                class="white--text ml-0"
                color="purple"
                label
                small
              >
                BINGO!
              </v-chip>
              I finally came up with the idea of Vuetify and Material Design and how both can really save me, not much CSS invovled and I have I need
            </v-col>
          </v-row>
        </v-timeline-item>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>2 hours later</span>
        </v-timeline-item>

        <v-timeline-item
          class="mb-4"
          color="grey"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              I made up mind and decided to use Tailwind but eventually the build wasn't satisfying enough for me
            </v-col>
          </v-row>
        </v-timeline-item>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>3 hours later</span>
        </v-timeline-item>

        <v-timeline-item
          class="mb-4"
          color="grey"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              I built the whole thing with Chakra but thought of compatibility and the how non-stable it was
            </v-col>
          </v-row>
        </v-timeline-item>

        <v-timeline-item
          class="mb-6"
          hide-dot
        >
          <span>2 hours in</span>
        </v-timeline-item>

        <v-timeline-item
          color="grey"
          small
        >
          <v-row justify="space-between">
            <v-col cols="7">
              I was researching the UI for maximum performance and considering some edits
            </v-col>
          </v-row>
        </v-timeline-item>
      </v-timeline>
    </v-container>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    educations: [
      {
        from       : '2019',
        to         : '2022',
        title      : 'Bachelor\'s degree, Computer Science',
        location   : 'University of Florida',
        description: 'Might seek a masters later, idk.',
      },
    ],
    experience: [
      {
        from       : '05/2021',
        to         : '01/2021',
        title      : 'Full Stack Solutions Engineer, Kingsmen Agency',
        location   : 'Remote',
        description: 'Built full-stack web software in React and Vue, including back-end services, data models, and front-end components that extend technical reach with customers and users, along with many other stuff',
      },
      {
        from       : '04/2020',
        to         : '01/2021',
        title      : 'Full Stack Engineer, Network Solutions',
        location   : 'Remote',
        description: 'Managed all stages of the creation from initial design and architecture to development, Improved product aesthetic and UX of the high-volume customers-facing portal, resulting in 40% increase in users’ retention \'exactly what I\'m doing with you now hehe\'',
      },
      {
        from       : '11/2019',
        to         : '04/2020',
        title      : 'Cyber Security Specialist, BBI CONSULTANCY',
        location   : 'Remote',
        description: 'NDA won\'t let me say anything, sorry :\"\" ',
      },
      {
        from       : '05/2018',
        to         : '10/2019',
        title      : 'Full Stack Engineer, Saber Agency',
        location   : 'Remote',
        description: 'I was a member of a team that constructed both the customer facing and administrative sites for their businesses. I was responsible for both front and back-end development. We used a collection of technologies for our underlying structures. There, my knowledge of HTML, CSS, JavaScript and Java expanded, while I gained experience using some of the best modern frameworks and technologies such as Bootstrap, Angular, NoSQL, PostgreSQL, Node.js and NPM.',
      },
    ],
    skills: [
      {
        title: 'PHP',
        value: 95,
      },
      {
        title: 'JavaScript',
        value: 80,
      },
      {
        title: 'Laravel',
        value: 90,
      },
      {
        title: 'Vue',
        value: 90,
      },
      { divider: true },
      {
        title: 'React',
        value: 90,
      },
      {
        title: 'Design Patters',
        value: 67,
      },
      {
        title: 'Cyber Security',
        value: 80,
      },
      {
        title: 'DevOps',
        value: 70,
      },
      {
        title: 'CI/CD',
        value: 50,
      },
      {
        title: 'Git',
        value: 90,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
