<template>
  <div>
    <div class="row">
      <div class="col-sm-12 col-md-8 text-left">
        <h4>{{region.name}}</h4>
        <p>
          <em>{{region.description}}</em>
        </p>
      </div>
      <div class="col-sm-12 col-md-4">
        <img :src="region.map" alt usemap="#regionMap" />
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
          <md-app-toolbar class="md-transparent" md-elevation="2">
            <md-button class="md-icon-button" @click="toggleMenu" v-if="!menuVisible">
              <md-icon>menu</md-icon>
            </md-button>
          </md-app-toolbar>
          <md-app-drawer :md-active.sync="menuVisible" md-persistent="mini">
            <md-toolbar class="md-transparent" md-elevation="2">
              <md-button class="md-icon-button" @click="toggleMenu" v-if="!menuVisible">
                <md-icon>menu</md-icon>
              </md-button>
              <span class="md-title">{{ choosenCDC.name }}</span>
              <div class="md-toolbar-section-end">
                <md-button class="md-icon-button md-dense" @click="toggleMenu">
                  <md-icon>keyboard_arrow_left</md-icon>
                </md-button>
              </div>
            </md-toolbar>

            <md-list>
              <md-list-item
                v-for="(item, index) in subject"
                :key="index"
                @click="changeSubject(index)"
              >
                <md-icon>{{ item.icon }}</md-icon>
                <span class="md-list-item-text">{{ item.subject }}</span>
              </md-list-item>
            </md-list>
          </md-app-drawer>

          <md-app-content>
            <div class="row">
              <div class="col-sm-7">
                <h5 class="card-header">{{ choosenSubject }}</h5>
                <p class="text-left">
                  {{ choosenCDC[choosenSubject] }}
                  Djibouti, le 20 Janvier 2020
                  A
                  Messieurs, le lieutenant-colonel Mahamoud, et le capitaine Mahdi Abdallah
                  Objet : Demande de considération des diplômes respectifs pour les fonctions occupées.
                  Suite à la décision présidentielle de notre recrutement prise le 9 Janvier, nous avons pris connaissance par le biais de notre supérieur hiérarchique, nos grades et nos salaires. Nous tenons par cette présente lettre à exprimer notre profonde déception vis-à-vis de la rémunération des fonctions que nous occupons et nous demandons la considération de nos diplômes respectifs.
                  Nous avons conscience de l’importance de notre mission et nous sommes plus que motivés à remplir nos fonctions respectives et à servir notre patrie. Nous vous demandons, monsieur le Lieutenant-Colonel Mahamoud, ainsi que monsieur le capitaine Mahdi Abdallah de nous aider à obtenir les rémunérations que nous octroie le Décret N° 2016-302/PR/MTRA portant sur la création du statut particulier des ingénieurs et spécialistes en Technologies de l'Information et des Communications de l'Etat, et de nous permettre de toucher les indemnités qui sont liés à nos fonctions.
                  Nous attachons à ce courrier les noms, diplômes et signatures de toutes les personnes concernées.
                  PJ : Décision présidentielle, liste des personnes concernées, et décret présidentiel.
                </p>
              </div>
              <div class="col-sm-5">
                Djibouti, le 20 Janvier 2020
                A
                Messieurs, le lieutenant-colonel Mahamoud, et le capitaine Mahdi Abdallah
                Objet : Demande de considération des diplômes respectifs pour les fonctions occupées.
                Suite à la décision présidentielle de notre recrutement prise le 9 Janvier, nous avons pris connaissance par le biais de notre supérieur hiérarchique, nos grades et nos salaires. Nous tenons par cette présente lettre à exprimer notre profonde déception vis-à-vis de la rémunération des fonctions que nous occupons et nous demandons la considération de nos diplômes respectifs.
                Nous avons conscience de l’importance de notre mission et nous sommes plus que motivés à remplir nos fonctions respectives et à servir notre patrie. Nous vous demandons, monsieur le Lieutenant-Colonel Mahamoud, ainsi que monsieur le capitaine Mahdi Abdallah de nous aider à obtenir les rémunérations que nous octroie le Décret N° 2016-302/PR/MTRA portant sur la création du statut particulier des ingénieurs et spécialistes en Technologies de l'Information et des Communications de l'Etat, et de nous permettre de toucher les indemnités qui sont liés à nos fonctions.
                Nous attachons à ce courrier les noms, diplômes et signatures de toutes les personnes concernées.
                PJ : Décision présidentielle, liste des personnes concernées, et décret présidentiel.
              </div>
            </div>
          </md-app-content>
        </md-app>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PersistentMini",
  data: function() {
    return {
      menuVisible: false,
      region: [],
      cdc: [
        {
          id: 2,
          name: "Khor-Angar",
          coord: "243, 126, 14",
          Description:
            "Ici se place la description complete du CDC de Khor-Angar",
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
    toggleMenu() {
      this.menuVisible = !this.menuVisible;
    },
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
    const townId = this.$route.query.townId;

    axios
      .post("https://sejs-backend.herokuapp.com/getTown", {
        townId: townId
      })
      .then(data => {
        this.region = data.data[0];
      })
      .catch(() => {
        this.$router.push({ path: "/" });
      });
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
.md-app {
  min-height: 350px;
  border: 1px solid rgba(#000, 0.12);
}
</style>
