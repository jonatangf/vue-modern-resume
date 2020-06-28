<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Who am I?"
      >
        I'm an enthusiastic agilist with a strong technical background, who believes in people and teamwork, and the
        change that these two can bring to society and organizations. As a Company Technical Lead I am used to work in
        multicultural environments, both collocated and distributed. My key skills include, but are not limited to;
        participating in high-level project technical definition and planning, transferring ideas into practical action
        and making sure that all team members understand business goals.
      </content-section>
      <content-section
        v-if="false"
        title="What am I proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
            </p>
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
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
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
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
      <content-section
        v-if="certifications"
      >
        <v-layout
          v-for="(certification, i) in certifications"
          :key="i"
        >
          <v-flex md4>
            {{ certification.from }} - {{ certification.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="certification.title">{{ certification.title }}</strong>
            <div v-if="certification.location">
              <i>{{ certification.location }}</i>
            </div>
            <div v-if="certification.description">
              {{ certification.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-help-rhombus-outline',
        text  : 'Answered 10M+ questions!',
        source: '(Bytegate.ir post views)',
      },
      {
        icon  : 'mdi-library-music',
        text  : 'Made people enjoy and learn a new language for equivalent of 29+ years (older than myself!)',
        source: '(Bobet.ir and its channel downloads)',
      },
      {
        icon  : 'mdi-timer-sand',
        text  : 'Saved +110 days of time of students, writers and etc!',
        source: '(Delix.ir service usages)',
      },
      {
        icon  : 'mdi-account-multiple',
        text  : 'Tried to cover small part of 7 people expenses.',
        source: '(My awesome colleagues)',
      },
    ],
    educations: [
      {
        from       : '2017',
        to         : 'present',
        title      : 'Master\'s Degree in Software Engineering and Computer Systems',
        location   : 'UNIR',
        description: '',
      },
      {
        from       : '2008',
        to         : '2013',
        title      : 'Degree in Computer Engineering, specialty in Software Engineering',
        location   : 'Las Palmas de Gran Canaria University',
        description: '',
      },
    ],
    skills: [
      {
        title: 'Java',
        icon : 'mdi-language-java',
        value: 100,
      },
      {
        title: 'NodeJS',
        icon : 'mdi-nodejs',
        value: 80,
      },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 90,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 60,
      },
      {
        title: 'Android',
        icon : 'mdi-android',
        value: '75',
      },
      {
        title: 'RabbitMQ',
        icon : 'mdi-rabbit',
        value: 80,
      },
      { divider: true },
      {
        title: 'Test Driven Development',
        icon : 'mdi-test-tube',
        value: 70,
      },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 60,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 90,
      },
      {
        title: 'Docker',
        icon : 'mdi-docker',
        value: 70,
      },
      { divider: true },
      {
        title: 'Agile',
        icon : 'mdi-truck-delivery',
        value: 90,
      },
      {
        title: 'Leadership',
        icon : 'mdi-account-group',
        value: 68,
      },
    ],
    certifications: [],
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
