<template>
  <v-container>
    <v-card class="mx-auto">
      <v-container>
        <v-row dense>

          <v-col cols="12">
            <v-card color="orange darken-4" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5">
                    Descripcion del proyecto
                  </v-card-title>

                  <v-card-subtitle>
                    Un proyecto FontEnd que muestra el uso de VueJs y Vuetify, en el cual se puede observar la navegacion entre pestañas,
                    y la interaccion con los componentes de Vuetify, asi como el uso de iconos de Material Design y otros url de paginas externas.
                  </v-card-subtitle>
                </div>
                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="../assets/logo.png"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>


          <v-col cols="12">
            <v-card color="#385F73" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5">
                    Formacion Academica
                  </v-card-title>

                  <v-card-subtitle>
                    Tengo una formacion universitaria en la Universidad Nacional Autonoma de México, en la carrera de
                    Ingenieria en Computacion.
                    Me estoy especializando en el desarrollo de paginas web y posteriormente en el desarrollo movil,
                    haciando un diplomado en Swift para IOS.
                  </v-card-subtitle>

                  <v-card-actions>
                    <v-btn text @click="sitioFi">
                      Sitio web
                    </v-btn>
                  </v-card-actions>
                </div>
                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="../assets/fi.jpg"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>

          <v-col cols="12">
            <v-card color="green" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5"> Lenguajes </v-card-title>

                  <v-card-subtitle> Python, javaScript, NodeJs, Vuejs, SQLserver...</v-card-subtitle>
                  <v-card-subtitle> Son algunos de los lenguajes con los que he trabajado y he obtenido experiencia asi
                    como realizado proyectos en el ambito
                    estudiantil y laboral.
                  </v-card-subtitle>
                </div>

                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="https://cdn.vuetifyjs.com/images/cards/foster.jpg"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>


          <v-col cols="12">
            <v-card color="blue" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5">
                    GitHub
                  </v-card-title>

                  <v-card-subtitle>
                    En este lugar encontrara algunos proyectos que he realizado como parte de mi formacion academica.
                    Tambien constantemente sigo creando proyectos o resolviendo ejercicios que estan de manera publica
                    para poder aprender o solo observar mis conocimientos
                    que siguen siendo adquiridos.
                  </v-card-subtitle>

                  <v-card-actions>
                    <v-btn text @click="repoGit">
                      Sitio web
                    </v-btn>
                  </v-card-actions>
                </div>
                <v-avatar class="ma-3" size="125" tile>
                  <v-img src="../assets/GitHub.png"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>

          <!-- <v-col v-for="(item, i) in items" :key="i" cols="12">
            <v-card :color="item.color" dark>
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="text-h5" v-text="item.title"></v-card-title>

                  <v-card-subtitle v-text="item.artist"></v-card-subtitle>

                  <v-card-actions>
                    <v-btn v-if="item.artist === 'Ellie Goulding'" class="ml-2 mt-3" fab icon height="40px" right
                      width="40px">
                      <v-icon>mdi-play</v-icon>
                    </v-btn>

                    <v-btn v-else class="ml-2 mt-5" outlined rounded small>
                      START RADIO
                    </v-btn>
                  </v-card-actions>
                </div>

                <v-avatar class="ma-3" size="125" tile>
                  <v-img :src="item.src"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col> -->
        </v-row>
      </v-container>
    </v-card>
  </v-container>
</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  data: () => ({
    sitioUnam: 'https://www.ingenieria.unam.mx/nuestra_facultad/imagen_institucional.php',
    items: [
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
        title: 'Supermodel',
        artist: 'Foster the People',
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
        title: 'Halcyon Days',
        artist: 'Ellie Goulding',
      },
    ],
  }),
  methods: {
    sitioFi() {
      window.open('https://www.ingenieria.unam.mx/nuestra_facultad/imagen_institucional.php')
    },
    repoGit() {
      window.open('https://github.com/AliHCS')
    }
  },
}
</script>
