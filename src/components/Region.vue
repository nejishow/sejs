<template>
  <div>
    <div class="row">
      <div class="col-sm-12 col-md-8 text-left">
        <h4>Obock</h4>
        <p>
          <em>
            Obock (également Obok, Afar: Hayyú) est une petite ville portuaire
            de Djibouti. Elle est située sur la rive nord du golfe de Tadjourah,
            où elle s'ouvre sur le golfe d'Aden. La ville abrite une piste
            d'atterrissage et dispose de ferries pour la ville de Djibouti,
            tandis que les mangroves se trouvent à proximité. Le nom francais
            Obock dérive de l'arabe "Oboh", déformation d'Oboki, nom donné à
            l'oued Dar'i dans sa partie médiane, en amont de son delta côtier.
          </em>
        </p>
      </div>
      <div class="col-sm-12 col-md-4">
        <img src="../assets/obockseul.jpg" alt="" usemap="#regionMap" />
        <map id="map" name="regionMap">
          <area
            v-for="(ville, index) in cdc"
            :key="index"
            shape="circle"
            :coords="ville.coord"
            href
            :alt="ville.name"
            class="area"
          />
        </map>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-12">
        <md-app>
          <md-app-drawer
            :md-active.sync="showNavigation"
            md-swipeable
            md-permanent="clipped"
          >
            <md-toolbar class="md-transparent" md-elevation="2">
              <span class="md-title">{{ choosenCDC.name }} </span>
            </md-toolbar>

            <md-list>
              <md-list-item>
                <md-icon>info</md-icon>
                <span class="md-list-item-text">Description</span>
              </md-list-item>

              <md-list-item>
                <md-icon>house</md-icon>
                <span class="md-list-item-text">Infrastructure</span>
              </md-list-item>
              <md-list-item>
                <md-icon>sports_soccer</md-icon>
                <span class="md-list-item-text">Activités</span>
              </md-list-item>
              <md-list-item>
                <md-icon>people_outline</md-icon>
                <span class="md-list-item-text">Personel</span>
              </md-list-item>

              <md-list-item>
                <md-icon>today</md-icon>
                <span class="md-list-item-text">Horraires</span>
              </md-list-item>
              <md-list-item>
                <md-icon>message</md-icon>
                <span class="md-list-item-text">Communiqués</span>
              </md-list-item>
            </md-list>
          </md-app-drawer>

          <md-app-content>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place la description complete du CDC</p>
            </div>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place l'Infrastructure complete du CDC</p>
            </div>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place les activités du CDC</p>
            </div>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place le personnel complete du CDC</p>
            </div>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place les horraires du CDC</p>
            </div>
            <div>
              <h6 class="card-header text-left">Section</h6>
              <p>Ici se place les communiqués du CDC</p>
            </div>
            <button @click="test">test</button>
          </md-app-content>
        </md-app>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      showNavigation: false,
      showSidepanel: false,
      region: [
        {
          name: "Obock",
          description: ""
        }
      ],
      cdc: [
        {
          name: "Khor-Angar",
          coord: "243, 126, 14",
          description: "Ici se place la description complete du CDC",
          activité: "ici les activités",
          personel: "ici le personel",
          horraires: "ici les horaires",
          communiqués: "ici les communiqués"
        },
        {
          name: "Obock",
          coord: "240, 275, 14"
        }
      ],
      choosenCDC: this.cdc[0]
    };
  },
  methods: {
    test() {
      console.log(this.cdc[0]);
    },
    created() {

    }
  }
};
</script>

<style lang="css" scoped>
.page-container {
  min-height: 300px;
  overflow: hidden;
  position: relative;
  border: 1px solid rgba(#000, 0.12);
}

.md-drawer {
  width: auto;
  max-width: calc(100vw - 125px);
  height: auto;
}

.md-content {
  padding: 16px;
}
</style>
