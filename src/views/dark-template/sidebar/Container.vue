<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Jonatan <span class="light-blue--text text--lighten-3">García</span>
        </h1>
        <span>
          A challenge-loving software engineer
        </span>
      </div>

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
              text: 'jntngf@gmail.com',
            },
            {
              name: 'Habitation',
              icon: 'mdi-map-marker',
              text: 'Canary Islands, Spain',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-linkedin',
              text: 'linkedin.com/in/jgarciaferrera',
              link: 'https://www.linkedin.com/in/jgarciaferrera/',
            },
            {
              icon: 'mdi-alpha-m',
              text: 'medium.com/@jntngf',
              link: 'https://medium.com/@jntngf',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            {
              icon: 'mdi-bullseye',
              text: 'Getting out of Safe Zone',
            },
            {
              icon: 'mdi-biohazard',
              text: 'Challenges',
            },
            {
              icon: 'mdi-image-filter-hdr',
              text: 'Nature',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Hacking Stuffs',
            },
            {
              icon: 'mdi-teach',
              text: 'Teaching',
            },
            {
              icon: 'mdi-ski-water',
              text: 'Kitesurf',
            },
            {
              icon: 'mdi-music',
              text: 'Music',
            },
            {
              icon: 'mdi-account-group',
              text: 'Leadership',
            },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            },
            {
              icon: 'mdi-motorbike',
              text: 'Z900!',
            },
            {
              icon: 'mdi-swim',
              text: 'Swimming',
            },
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text : 'Spanish',
              value: 100,
            },
            {
              text : 'English',
              value: 80,
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
