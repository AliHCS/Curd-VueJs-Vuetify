import { Router } from 'express';
<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">

        <v-icon class="mx-2" dark @click="drawer = true">
          mdi-format-list-bulleted-square
        </v-icon>

        <h2 class="pa-3">App con Vuetify</h2>
      </div>
      <v-spacer></v-spacer>
      <v-dialog transition="dialog-bottom-transition" max-width="600" v-if="this.$route.name === 'tareasCrud'">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="green darken-4" v-bind="attrs" v-on="on">Informacion</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar color="green darken-4" dark>Crud de Tareas</v-toolbar>
            <v-card-text>
              <div class="mt-10">Un programa de tareas con las operaciones de crear, leer, editar y borrar, tiene unas
                de ejemplo de como se ven.
              </div>
              <div>Deben llevar un titulo y una descripcion de dicha tarea, se cuanta con mensajes de alerta para los
                casos en que se agrege una nueva tarea, no se llene nada y se mande, tambien si se elimina.
              </div>
              <div>Todo es de forma local, pero podria implementarse el uso de una base de datos para hacer la
                informacion persistente, asi como un documento tipo JSON.
              </div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn color="error" text @click="dialog.value = false">Cerrar</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="./assets/imgPerfil.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Gustavo Ali Gómez Trejo</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item link block :to="{name: 'home'}">
          <v-list-item-icon>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link block :to="{name: 'tareasCrud'}">
          <v-list-item-icon>
            <v-icon>mdi-forum</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Tareas Crud</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
    drawer: false,
    dialog: false,
    items: [
      { title: 'Home', icon: 'mdi-view-dashboard' },
    ],
  })
};
</script>
