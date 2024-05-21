<template>
  <main>
    <v-app-bar
      color="#ffffff"
      clipped-left
      clipped-right
      app
      fixed
      height="100px"
    >
    <!-- las imagenes van en static -->
      <v-img src="/logo.png" class="logo1v"></v-img>

      <v-btn icon @click="drawer = !drawer" class="menu-button">
        <v-icon>mdi-menu</v-icon>
      </v-btn>

      <div class="nav-buttons-container">
        <div class="nav-buttons">
          <v-btn class="nav" href="#inicio" elevation="0">Inicio</v-btn>
          <v-btn class="nav" href="#productos" elevation="0">Productos</v-btn>
          <v-btn class="nav" href="#nosotros" elevation="0">Nosotros</v-btn>
          <v-btn class="nav" href="#contactanos" elevation="0"
            >Contáctanos</v-btn
          >
        </div>
      </div>
    </v-app-bar>
    <!-- el menu drawer va  -->
    <v-navigation-drawer v-if="$vuetify.breakpoint.mdAndDown" v-model="drawer" fixed temporary>
      <v-list>
        <v-list-item href="#inicio">Inicio</v-list-item>
        <v-list-item href="#productos">Productos</v-list-item>
        <v-list-item href="#nosotros">Nosotros</v-list-item>
        <v-list-item href="#contactanos">Contáctanos</v-list-item>
      </v-list>
    </v-navigation-drawer>
  </main>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
    };
  },
};
</script>

<style scoped>
.logo1v {
  max-width: 130px;
  max-height: 90px;
  width: auto;
  height: auto;
}

.menu-button {
  display: none;
}

.drawer {
  width: 200px;
}

.nav-buttons-container {
  display: flex;
  justify-content: flex-end;
  margin-left: 30%;
}

.nav-buttons {
  display: flex;
}

@media only screen and (max-width: 600px) {
  .nav-buttons-container {
    display: none;
  }

  .app-bar-row {
    flex-direction: row-reverse;
  }

  .menu-button {
    display: block;
    z-index: 1;
    color: rgb(0, 136, 255);
    margin-left: auto;
  }

  .drawer {
    width: 250px;
    z-index: 3;
    right: 0;
    left: auto;
  }
}
</style>
