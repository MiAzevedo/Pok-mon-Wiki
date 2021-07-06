 <template>
  <q-layout view="hHh Lpr lff" class="shadow-2 rounded-borders">
    <q-header elevated>
      <q-toolbar class="glossy">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-toolbar-title>
          P <q-img src="~assets/pokeball.png" class="pokeball_img" />
          kémon Wiki
        </q-toolbar-title>

        <div>v 1.0</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above :width="200">
      <q-scroll-area class="fit">
        <q-list padding class="menu-list">
          <q-item clickable v-ripple to="/">
            <q-item-section avatar class="pokeball_section">
              <q-img src="~assets/super-ball.png" class="pokeball_menu" />
              <!-- <q-icon name="home" /> -->
            </q-item-section>

            <q-item-section> Home </q-item-section>
          </q-item>
          <q-item clickable v-ripple to="/pokemon">
            <q-item-section avatar class="pokeball_section">
              <q-img src="~assets/ultra-ball.png" class="pokeball_menu" />
              <!-- <q-icon name="home" /> -->
            </q-item-section>

            <q-item-section> Pokémons </q-item-section>
          </q-item>
          <q-item clickable v-ripple to="/item">
            <q-item-section avatar class="pokeball_section">
              <q-img src="~assets/mega-ball.png" class="pokeball_menu" />
              <!-- <q-icon name="home" /> -->
            </q-item-section>

            <q-item-section> Itens </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container> <router-view /> </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {
      leftDrawerOpen: false,
    };
  },
  methods: {
    toggleLeftDrawer() {
      //  this.leftDrawerOpen = !this.leftDrawerOpen
      if (this.leftDrawerOpen == true) {
        this.leftDrawerOpen = false;
      } else {
        this.leftDrawerOpen = true;
      }
    },
  },
};
</script>

<style >
.pokeball_img {
  width: 25px;
  margin-left: -5px;
  margin-right: -5px;
}
.pokeball_menu {
  width: 20px;
}
.pokeball_section {
  margin-right: -20px;
}
.menu-list .q-item {
  border-radius: 0 32px 32px 0;
}
</style>