<template>
  <div>
    <div class="row">
      <div class="col-sm-12 text-left">
        <img src="../assets/facebook.png" width="30" height="auto" alt="" style="border:solid black 1px;padding:5px; margin-right:5px" />
        <img src="../assets/instagram.png" width="30" height="auto" alt="" style="border:solid black 1px;padding:5px; margin-right:5px" />
        <img src="../assets/twitter.png" width="30" height="auto" alt="" style="border:solid black 1px;padding:5px; margin-right:5px" />
        <img src="../assets/youtube.png" width="30" height="auto" alt="" style="border:solid black 1px;padding:5px; margin-right:5px"/>
      </div>
    </div>

    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">
        <img src="../assets/logo.png" width="50" height="auto" alt="" />
      </a>
      <span>SECRETARIAT D'ETAT A LA JEUNESSE ET AUX SPORTS</span>
      <div class="filler"></div>

      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item active">
            <a class="nav-link" href="#">Acceuil </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Programmes</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Services</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contact</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">A propos de nous</a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>
<style lang="css">
nav {
  border: solid black 1px;
}
.filler {
  flex: 1 1 auto;
}
</style>
