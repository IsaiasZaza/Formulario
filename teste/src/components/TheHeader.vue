<template>
    <header>
        <h1 :class="{ 'title': false, 'title-home': isHome }">Curso Vue</h1>
    </header>
    <div>
        <img src="https://placehold.co/600x400" v-bind:alt="imgAlt">
    </div>
    <div>
        Two-way data binding
        v-model -> formularios
    </div>
   <div>
    <br>
    <label>Nome</label>
    <input type="text" v-model="name">
    <br>
    {{ name }}
   </div>

   <br>
   <div>
    <label>Sports</label>
    <select v-model="sports">
        <option value="">Escolha</option>
        <option value="futebol">Futebol</option>
        <option value="volei">Volei</option>
        <option value="Skate">Skate</option>
        Tenis
    </select>
    {{ sports }}
   </div>

   <div>
    <label>NewsLetter</label><br>
    <input type="radio" value="Sim" v-model="NewsLetter">Sim
    <input type="radio" value="Não" v-model="NewsLetter">Não
    {{ NewsLetter }}

   </div>

   <div>
    <button @click="onclick"> <!--ou v-on:-->
        Enviar
    </button>
    <br>
    <div @mouseover="onMouse" @mouseout="onOut">
        Mouse over
    </div>
   </div>
   <br>
   <br>
   <form action="httpm://google.com" @submit="onsubmit">
<button type="submit">,
        Enviar
    </button>
</form>
    

    <!--<div>
        <div v-for="local in todos" v-bind:key="local.id" class="todos-item">
            {{ local.title }}
        </div>
    </div>-->
    
    <p :class="[{'text': false, 'text-home': isHome}]">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis totam quaerat consequuntur illum obcaecati vitae iste
        voluptate nulla, fuga mollitia iusto unde, eos est sequi beatae corporis aliquid ad cum.
    </p>
</template>

<script lang="ts">


export default {
    name: 'TheHeader',
    data() {
        return {
            NewsLetter: '',
            pClass: 'text',
            sports: '',
            isHome: true,
            classVar: 'title',
            imgAlt: 'JonSnow',
            name: ''
        }
    },
    methods: {
        onclick() {
            console.log('Clicou')
        },
        onMouse(){
            console.log('aaaaaaaaaaaaaaaaaaaaaaaa')
        },
        onOut(){
            console.log('bbbbbbbbbbbb')
        },
        onsubmit(){
            console.log('suba')
        }
        }
}




</script>
    
<style>
.text-home{
    color: wheat;
}
.text{
    color: red;
}
.title-home {
    font-size: 80px;
    color: green;
}

.title {
    font-size: 20px;
    color: blue;
}

.header {
    color: #fff;
}

.todos-item {
    background-color: black;
    color: white;
    text-align: left;
    padding: 8px;

}
</style>