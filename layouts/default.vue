<template>
  <v-app>
    <v-navigation-drawer v-model="sidebar" app>
      <v-list>
        <v-list-tile
          v-for="item in menuItems"
          :key="item.title"
          :to="item.path">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>{{ item.title }}</v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar app dark color="grey darken-2">
      <span class="hidden-sm-and-up">
        <v-toolbar-side-icon @click="sidebar = !sidebar">
        </v-toolbar-side-icon>
      </span>
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">
          {{ appTitle }}
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn
          flat
          v-for="item in menuItems"
          :key="item.title"
          :to="item.path">
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    
    <v-content>
      <nuxt/>
    </v-content>
    <v-footer
    height="auto"
    color="grey darken-4"
  >
    <v-layout
      justify-center
      row
      wrap
    >
    
      <v-flex
        dark
        lighten-2
        py-3
        text-xs-center
        white--text
        xs12
      >
        &copy;2018 — <strong>Srcman</strong>
      </v-flex>
    </v-layout>
  </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        appTitle: 'Srcman',
        sidebar: false,
        menuItems: [
          { title: 'Committee', path: '/home' },
          { title: 'Gallery', path: '/signup' },
          { title: 'News', path: '/signin' },
          { title: 'About', path: '/signin' },
          { title: 'Contact', path: '/signin' }
        ],
        icons: [
        'fab fa-facebook',
        'fab fa-twitter',
        'fab fa-google-plus',
        'fab fa-linkedin',
        'fab fa-instagram'
      ]
      }
    }
  }
</script>