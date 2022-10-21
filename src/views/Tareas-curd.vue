<template>
    <div>
        <v-container grid-list-md>
            <v-layout>
                <v-flex md6>
                    <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
                        <v-card-text>
                            <v-chip class="ma-2 ml-0" color="pink" label text-color="white">
                                <v-icon left>
                                    mdi-label
                                </v-icon>
                                {{item.titulo}}
                            </v-chip>
                            <p>{{item.descripcion}}</p>
                            <v-btn color="warning" class="ml-0" @click="editar( index )">editar</v-btn>
                            <v-btn color="error" class="ml-5" @click="eleminarTarea(item.id)">eliminar</v-btn>
                        </v-card-text>
                    </v-card>
                </v-flex>
                <v-flex md6 v-if="formAgregar">
                    <v-card class="mb-3 pa-3">
                        <v-form @submit.prevent="agregarTarea()">
                            <v-text-field v-model="titulo" label="Titulo de la tarea" required></v-text-field>
                            <v-textarea label="Descripcion de Tarea" v-model="descripcion"></v-textarea>
                            <v-btn block color="success" type="submit">Agregar Tarea</v-btn>
                        </v-form>
                    </v-card>
                </v-flex>

                <v-flex md6 v-if="!formAgregar">
                    <v-card class="mb-3 pa-3">
                        <v-form @submit.prevent="editarTarea()">
                            <v-text-field v-model="titulo" label="Titulo de la tarea" required></v-text-field>
                            <v-textarea label="Descripcion de Tarea" v-model="descripcion"></v-textarea>
                            <v-btn block color="warning" type="submit">Editar Tarea</v-btn>
                        </v-form>
                    </v-card>
                </v-flex>
            </v-layout>
            <v-snackbar v-model="snackbar">
                {{ message }}
                <template v-slot:action="{ attrs }">
                    <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
                        Cerrar
                    </v-btn>
                </template>
            </v-snackbar>
        </v-container>
    </div>
</template>

<script>

export default {
    components: {

    },
    data() {
        return {
            titulo: '',
            descripcion: '',
            message: 'jejejejejejejej',
            snackbar: false,
            formAgregar: true,
            indexTarea: '',
            listaTareas: [
                {
                    id: 1, titulo: 'Titulo 1', descripcion: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt officiis sint quia consequuntur voluptatibus cumque ipsa sequi ad.Odio obcaecati, dolorum excepturi harumillum repellat dolores.'
                },
                {
                    id: 2, titulo: 'Titulo 2', descripcion: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt officiis sint quia consequuntur voluptatibus cumque ipsa sequi ad.Odio obcaecati, dolorum excepturi harumillum repellat dolores.'
                }
            ]
        }
    },
    methods: {
        agregarTarea() {
            if (this.titulo === '' || this.descripcion === '') {
                this.snackbar = true
                this.message = 'Llena todos los campos'

            } else {
                this.listaTareas.push({
                    id: Date.now(),
                    titulo: this.titulo,
                    descripcion: this.descripcion
                })
                this.titulo = ''
                this.descripcion = ''
                this.snackbar = true
                this.message = 'Tarea Agregada'
            }
        },
        eleminarTarea(id) {
            this.listaTareas = this.listaTareas.filter(elem => {
                return elem.id !== id
            })
            this.snackbar = true
            this.message = 'Tarea Eliminada'
        },
        editar(index) {
            this.formAgregar = false
            this.titulo = this.listaTareas[index].titulo
            this.descripcion = this.listaTareas[index].descripcion
            this.indexTarea = index
        },
        editarTarea() {
            this.listaTareas[this.indexTarea].titulo = this.titulo
            this.listaTareas[this.indexTarea].descripcion = this.descripcion
            this.formAgregar = true
            this.titulo = ''
            this.descripcion = ''
            this.snackbar = true
            this.message = 'Tarea Editada'
        }
    },
};

</script>