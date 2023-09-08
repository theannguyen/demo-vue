<template>
    <div class="container">
        <div v-if="openClose" class="modal fade show" tabindex="-1" aria-labelledby="exampleModalLabel" aria-modal="true"
            role="dialog" style="display: block">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title">Demo Modal</h5>
                        <button @click="openCloseFunc()" type="button" class="btn-close" aria-label="Close"></button>
                    </div>
                    <div class="modal-body">
                        <input>
                    </div>
                    <div class="modal-footer">
                        <button @click="openCloseFunc()" type="button" :class="'btn btn-' + variant">Close</button>
                        <button @click="openCloseFunc()" type="button" :class="'btn btn-primary'">Save changes</button>
                    </div>
                </div>
            </div>
        </div>aaavdffsdfsd
        <button @click="openCloseFunc()" type="button" :class="'btn btn-success'">Open Modal</button>
    </div>
</template>

<script>
export default {
    name: 'Alert',
    props: {
        visible: Boolean,
        variant: String,
    },
    data() {
        return {
            openClose: this.visible
        }
    },
    methods: {
        openCloseFunc() {
            this.openClose = !this.openClose;
        }
    },
    watch: {
        visible: function (newValue, oldValue) {
            this.openClose = newValue
            console.log('new' + newValue + '==' + oldValue)
        }
    }
}
</script>