<template>
    <div>
        <input type="text" v-model="name"><br>
        {{ name }}
    </div>

    <br>
    <select v-model="pageCount">
        <option value="10">10</option>
        <option value="15">15</option>
        <option value="20">20</option>
    </select>
    {{ pageCount }}
</template>

<script lang="ts">




    export default {
        name: 'watch',
        data(){
            return{
                name: '',
                pageCount: '10'
            }
        },
        watch: {
            name(za) {
                if(za.length >= 3){
                this.saveUserName(); //observador
            }
        }
        },
        pageCount(){
            this.changePage();
        },

        computed: {

        },
        methods: {
            saveUserName(){
                console.log(this.name);
            },
            changePage() {
                console.log('trocou o nome')
            }
        }
    }
</script>