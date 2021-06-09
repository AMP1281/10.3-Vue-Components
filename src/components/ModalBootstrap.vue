<template>

    <div>

        <div id="ModalBootstrap" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog">
                <div class="modal-content">

                    <div class="modal-header">
                        <slot name="header"></slot>
                    </div>

                    <div class="modal-body d-flex flex-column justify-content-around align-items-center">
                        <slot name="body"></slot>
                    </div>

                    <div class="modal-footer">
                        <slot name="footer"></slot>
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