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

        <template v-slot:body="slotProps">
            <h2 class="mb-4">Cambio de moneda</h2>
            <p>El cambio de {{ slotProps.numero }}€ en dolares son {{ slotProps.numeroCurrency }}$</p>
            <p class="position-absolute fixed-bottom mb-3"></p>

        </template>

        <template v-slot:footer>
            <button @click="closeModal()" type="button" class="btn btn-secondary" data-dismiss="modal">Cerrar</button>
            <button @click="limpiar()" type="button" class="btn btn-primary">Borrar</button>
        </template>

    </ModalBootstrap>

    <p v-show="mostrar" class="mt-5">Heu tancat el modal</p>

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
            variable: '',
            mostrar:false
            }
    },
    methods:{
        openModal(){
            this.showModal = true;
            this.mostrar= false;
        },
        closeModal(){
            this.showModal = false;
            this.mostrar= true;
        },
        limpiar(){
            this.euros = ''
        }
    },
    
    
}

</script>