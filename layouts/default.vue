<template>
<!-- Layout de barra de navegación para las páginas -->
<div>
  <v-navigation-drawer
      v-model="drawer" app>
      <v-list-item>
       
        <v-list-item-content>
          <v-list-item-title>Menú</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item :to="item.route" v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title style="padding:5px">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  <v-app-bar dense>
    <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
    <v-toolbar-title>El Taller</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn @click="logout()">Salir</v-btn>
  </v-app-bar>
  <v-main>
    <v-container> 
      <nuxt /> 
    </v-container>
  </v-main>
</div>

</template>

<script>
export default {
  methods: {
    logout() {
      this.$router.push("/");
    }
  },
  data () {
      return {
        drawer: null,
        items: [
          { title: 'Home', icon: 'mdi-home', route: '/home' },
          { title: 'Users', icon: 'mdi-account-group', route: '/users' },
          { title: 'Motor', icon: 'mdi-motorbike', route: '/motorcycle' }
        ],
      }
    },
};
</script>
