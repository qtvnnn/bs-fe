<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <img
        src="~/assets/img/logo.png"
        class="img-logo my-12"
        alt="Vuetify.js"
      >
      <v-divider class="mb-7"></v-divider>
      <v-expansion-panels accordion>
        <v-expansion-panel>
          <v-expansion-panel-header class="pr-3">
            <div class="menu-panel-header px-8">
                <v-icon class="mr-3">mdi-laptop</v-icon>
                <span>MANAGE CYBER</span>
            </div>              
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            <v-list>
              <v-list-item
                v-for="(item, i) in items"
                :key="i"
                :to="item.to"
                router
                exact
              >
                <v-list-item-action>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                  <v-list-item-title v-text="item.title" />
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: '',
          title: 'Information',
          to: '/admin/information',
        },
        {
          icon: '',
          title: 'Room',
          to: '/admin/room',
        },
        {
          icon: '',
          title: 'Booking',
          to: '/admin/booking',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script>
<style lang="scss" scoped>
.img-logo {
    margin: auto;
    display: flex;  
}
.menu-panel-header {
    display: flex;
    align-items: center;
}
</style>