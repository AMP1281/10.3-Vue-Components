<template>

<div>
    
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary mt-3" data-bs-toggle="modal" data-bs-target="#exampleModal">
    Launch demo modal
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
        <div class="modal-content">
        <div class="modal-header">
            <slot></slot>
        </div>
        <div class="modal-body">
           <slot></slot>
        </div>
        <div class="modal-footer">
            <slot></slot>
        </div>
        </div>
    </div>
    </div>
</div>

</template>

<script>
export default {
  name: 'ModalBootstrap',
}
</script>