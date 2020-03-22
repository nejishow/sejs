<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-sm-12 text-left">
        <img
          src="../assets/facebook.png"
          width="30"
          height="auto"
          alt
          style="border:solid blue 1px;padding:5px; margin-right:5px"
        />
        <img
          src="../assets/instagram.png"
          width="30"
          height="auto"
          alt
          style="border:solid blue 1px;padding:5px; margin-right:5px"
        />
        <img
          src="../assets/twitter.png"
          width="30"
          height="auto"
          alt
          style="border:solid blue 1px;padding:5px; margin-right:5px"
        />
        <img
          src="../assets/youtube.png"
          width="30"
          height="auto"
          alt
          style="border:solid blue 1px;padding:5px; margin-right:5px"
        />
      </div>

      <div class="wrapper col-sm-12 navbar navbar-expand-lg">
        <a class="navbar-brand">
          <router-link to="/">
            <img src="../assets/logo.png" width="50" height="auto" alt />
          </router-link>
        </a>
        <span>SECRETARIAT D'ETAT A LA JEUNESSE ET AUX SPORTS</span>
        <div class="filler"></div>

        <b-navbar-toggle target="nav-collapse" class="navbar-toggler bg-dark text-light"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav tabs pills>
            <router-link to="/">
              <b-nav-item class="btn-group btn btn-outline-light">Acceuil</b-nav-item>
            </router-link>
            <router-link to="/">
              <b-nav-item class="btn-group btn btn-outline-light">Programme</b-nav-item>
            </router-link>
            <b-nav-item class="btn-group btn btn-outline-light">Services</b-nav-item>
            <b-nav-item class="btn-group btn btn-outline-light">A propos de nous</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </div>
  </div>
</template>
<style lang="css">
.filler {
  flex: 1 1 auto;
}
.wrapper {
  background: linear-gradient(90deg, #e3ffe7 0%, #d9e7ff 100%);
}
</style>
