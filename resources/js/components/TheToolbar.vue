<template>
  <div>
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list>
        <v-list-item
          v-for="(link, index) in links"
          :key="index"
          :to="link.to"
          exact
        >
          <v-list-item-action>
            <v-icon>
              {{ link.icon }}
            </v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ link.title }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      app
      dark
      color="primary"
      clipped-left
    >
      <v-toolbar-title
        class="headline"
      >
        <v-app-bar-nav-icon
          @click.stop="setDrawer(!drawer)"
        />
        Laravel SPA
      </v-toolbar-title>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
    };
  },
  computed: {
    links() {
      return [
        {
          title: this.$t('links.home'),
          icon: 'mdi-home',
          to: {
            name: 'home',
          },
        },
      ];
    },
  },
  methods: {
    setDrawer(drawer) {
      this.drawer = drawer;
    },
  },
};
</script>
