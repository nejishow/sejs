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
            href="#"
            shape="circle"
            :coords="ville.coord"
            :alt="ville.name"
            class="area"
            @click="changeTown(ville.id)"
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
              <md-list-item
                v-for="(item, index) in subject"
                :key="index"
                @click="changeSubject(index)"
              >
                <md-icon>{{ item.icon }} </md-icon>
                <span class="md-list-item-text">{{ item.subject }} </span>
              </md-list-item>
            </md-list>
          </md-app-drawer>

          <md-app-content>
            <h5 class="card-header">{{ choosenSubject }}</h5>
            <p class="text-left">{{ choosenCDC[choosenSubject] }}</p>
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
          id: 2,
          name: "Khor-Angar",
          coord: "243, 126, 14",
          Description: "Ici se place la description complete du CDC de Khor-Angar",
          Activités: "ici les activités",
          Infrastructure: "ici les infrastructures sont presentés",
          Personel: "ici le personel",
          Horraires: "ici les horaires",
          Communiqués: "ici les communiqués"
        },
        {
          id: 1,
          name: "Obock",
          coord: "240, 275, 14",
          Description: "Ici se place la description complete du CDC d'Obock",
          Activités: "ici les activités",
          Infrastructure: "ici les infrastructures sont presentés",
          Personel: "ici le personel",
          Horraires: "ici les horaires",
          Communiqués: "ici les communiqués"
        }
      ],
      subject: [
        { id: 1, icon: "info", subject: "Description" },
        { id: 2, icon: "house", subject: "Infrastructure" },
        { id: 3, icon: "sports_soccer", subject: "Activités" },
        { id: 4, icon: "people_outline", subject: "Personel" },
        { id: 5, icon: "today", subject: "Horraires" },
        { id: 6, icon: "message", subject: "Communiqués" }
      ],
      choosenCDC: "",
      choosenSubject: "Description"
    };
  },
  methods: {
    changeSubject(index) {
      this.choosenSubject = this.subject[index].subject;
    },
    changeTown(id) {
      this.cdc.forEach(element => {
        if (element.id == id) {
          this.choosenCDC = element;
        }
      });
    }
  },
  created() {
    this.choosenCDC = this.cdc[0];
    this.choosenCDC.subject = "Description";
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
