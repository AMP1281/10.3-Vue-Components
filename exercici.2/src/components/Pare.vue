
<template>

<div class="container">

    <button type="button" class="btn btn-primary" @click="openModal()" data-toggle="modal" data-target="#ModalBootstrap">Open modal</button>

    <ModalBootstrap v-if="showModal">

        <template v-slot:header>
        <h5 class="modal-title">Modal title</h5>
            <button  @click="showModal = false" type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
            </button>
        </template>

        <template v-slot:body>
            <p>Modal body text goes here.</p>
        </template>

        <template v-slot:footer>
            <button @click="showModal = false" type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
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
            showModal: false
        }
    },
    methods:{
        openModal(){
            this.showModal = true;
        }
    }
}

</script>
