<template>
  <v-container>
    <v-row class="pt-10" justify="center" align="center">
      <v-col cols="4">
        <v-img src="/image/hello4.svg"></v-img>
      </v-col>
      <v-col cols="8">
        <h1 class="my-3 font-weight-light">HELLO!</h1>
        <h2 class="mb-5 display-2 font-weight-bold">
          Je suis, <br />Maksymilian Czadowski
        </h2>
        <p class="mb-4 title font-weight-light">
          Web Developer & Mobile Application Developer
        </p>
        <v-row>
          <v-col cols="1">
            <a href="https://www.linkedin.com/in/maksymilian-czadowski/" target="blank">
              <v-icon>mdi-linkedin</v-icon>
            </a>
          </v-col>
          <v-col col="1">
            <a href="https://github.com/MaksymilianCzadowski" target="blank">
              <v-icon>mdi-github</v-icon>
            </a>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <div class="py-15"></div>
    <v-row justify="center" align="center">
      <v-col>
        <h2 class="title font-weight-bold mt-10 mb-3">
          Hello! Je suis Maksymilian Czadowski.
        </h2>
        <p>
          Je suis passionné par le web et les nouvelles technologies, j'ai la
          chance de pouvoir apprendre à développer mes compétences au sein
          d'Ynov Paris campus. Actuellement étudiant en 3ème années, je souhaite
          à terme devenir développeur web.
        </p>
        <br />
        <br />
        <div class="d-flex mt-2">
          <h4 class="font-weight-light mr-3 pt-1">Âge :</h4>
          <h3>19 ans</h3>
        </div>
        <div class="d-flex mt-2">
          <h4 class="font-weight-light mr-3 pt-1">Email :</h4>
          <h3>maksymilian.czadowski@gmail.com</h3>
        </div>
        <div class="d-flex mt-2">
          <h4 class="font-weight-light mr-3 pt-1">Adresse :</h4>
          <h3>Suresnes, Hauts-de-Seine</h3>
        </div>
        <div class="d-flex mt-2">
          <h4 class="font-weight-light mr-3 pt-1">Numéro :</h4>
          <h3>+33 7 51 09 01 49</h3>
        </div>
        <div class="d-flex mt-2">
          <h4 class="font-weight-light mr-3 pt-1">Status :</h4>
          <h3>Disponible</h3>
        </div>
      </v-col>
      <v-col>
        <v-img
          src="image/moi.jpeg"
          width="400"
          style="border-radius: 10%"
        ></v-img>
      </v-col>
    </v-row>
    <br />
    <br />
    <div class="mt-15">
      <h1 class="text-center display-2 font-weight-bold mt-15 mb-10">
        Mes Compétences
      </h1>
      <p class="mx-auto text-center title-1" style="max-width: 600px">
        J'apprends vite et je suis spécialisée dans la multitude de compétences
        requises pour le développement d'applications Web et la conception de
        produits.
      </p>
      <div class="bg-light p-3">
        <div class="row">
          <div class="col-md-5">
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">HTML5</span><span>80%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="hight"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">CSS3</span><span>70%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="medieum"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">JavaScript</span><span>70%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="medieum"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">VueJs</span><span>60%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="mid"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
          </div>
          <div class="col-md-5 offset-md-2">
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">PHP</span><span>80%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="hight"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">NuxtJs</span><span>65%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="mid"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">MySQL</span><span>60%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="low"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
            <div class="py-1">
              <div class="d-flex text-small fw-bolder">
                <span class="me-auto">Typescript</span><span>60%</span>
              </div>
              <div class="progress my-1">
                <v-progress-linear
                  v-model="low"
                  color="amber"
                  height="25"
                ></v-progress-linear>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <br />
    <br />
    <div class="mt-15">
      <h1 class="text-center display-2 font-weight-bold mt-15 mb-10">
        Mes Expérience
      </h1>
      <v-row>
        <v-col cols="6">
          <v-card>
              <v-card-title>Développeur Web</v-card-title>
              <v-card-text></v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  name: 'contact',
  layout: 'presentation',
  data: () => ({
    hight: 80,
    medieum: 70,
    mid: 75,
    low: 60,

  })
}
</script>

<style scoped>
a {
  text-decoration: none;
}
</style>
