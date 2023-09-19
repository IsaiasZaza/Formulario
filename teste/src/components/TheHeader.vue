<template>
    <header class="header">
        header
    </header>
    <div>
        <img 
        src="https://placehold.co/600x400" 
        v-bind:alt="imgAlt">
    </div>
    <div>
        <div v-for="local in todos" v-bind:key="local.id" class="todos-item">
            {{ local.title }}
        </div>
    </div>
</template>

<script lang="ts">
import App from '@/App.vue';

export default {
    name: 'App',
    data() {
        return {
            imgAlt: 'JonSnow',
            todos: [
                {
                    "userId": 1,
                    "id": 1,
                    "title": "delectus aut autem",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 2,
                    "title": "quis ut nam facilis et officia qui",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 3,
                    "title": "fugiat veniam minus",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 4,
                    "title": "et porro tempora",
                    "completed": true
                },
                {
                    "userId": 1,
                    "id": 5,
                    "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 6,
                    "title": "qui ullam ratione quibusdam voluptatem quia omnis",
                    "completed": false
                }]

        }
    }
}



</script>
    
<style>
.header {
    color: #fff;
}
.todos-item{
    background-color: black;
    color: white;
    text-align: left;
    padding: 8px;

}
</style>