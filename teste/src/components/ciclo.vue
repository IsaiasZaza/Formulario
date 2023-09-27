<template>
    <div :class="baseClass"> 
        
        <slot></slot>

        <button @click="onClick()">
            X
        </button>
    </div>
</template>
<script lang="ts">
export default {
    props: {
        variant: {
            type: String,
            default: ''
        },
    },
    computed: {
        baseClass() {
            return [
                'alert', 
                this.variant ? `alert-${this.variant}` : ''
            ]
        },
    },

    methods: {
        onClick(){
           this.$emit('close')
        }
    }
}
</script>

<style>
    .alert{
        padding: 8px;
        border-radius: 8px;
        background-color: palegoldenrod;
        color: black;
        font-weight: bold;
        text-align: center;
        display: flex;
        justify-content: space-between;
    }
    .alert-sucess {
        background-color: green;
        color: white;
    }

</style>