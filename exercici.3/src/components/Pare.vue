<template>

<div class="container">

    <button type="button" class="btn btn-primary mt-5" @click="openModal()" data-toggle="modal" data-target="#ModalBootstrap">Open modal</button>

    <ModalBootstrap v-if="showModal">

        <template v-slot:header>
        <h5 class="modal-title">Hola Mundo</h5>
            <button  @click="showModal = false" type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
            </button>
        </template>

        <template v-slot:body>
            <h2 class="mb-4">Cambio de moneda</h2>
            <input class="mb-5" v-model="euros" type="number" min="0" step="0.01" placeholder="Introduce euros €">
            <p v-show="euros>0" class="position-absolute fixed-bottom mb-3">El cambio de {{euros}}€ en dolares son {{euros | Currency}}$</p>
        </template>

        <template v-slot:footer>
            <button @click="showModal = false" type="button" class="btn btn-secondary" data-dismiss="modal">Cerrar</button>
            <button @click="limpiar()" type="button" class="btn btn-primary">Enviar</button>
        </template>

    </ModalBootstrap>

</div>

</template>


<script>

import ModalBootstrap from './ModalBootstrap.vue'

export default {
    name: 'Pare',
    components: {
        ModalBootstrap
    },
    data () {
        return{
            showModal: false,
            euros:''
        }
    },
    methods:{
        openModal(){
            this.showModal = true;
        },
        limpiar(){
            this.euros = ''
        }
    },
    filters:{
        Currency(euros){
            return euros*1.23
        }
    }
}

</script>
