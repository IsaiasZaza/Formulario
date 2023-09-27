
<template>
  <div> 
      <div>
        <TheHeaderVue />
      </div>

      <div>
        <watch>

        </watch>
      </div>
      <RouterView>
       
      </RouterView>
      
  </div>
  <div>
    <ciclo :variant="variant" @close="onClose()" v-if="showAlert">
    {{ text }}
    </ciclo>
    
  </div>
</template>

<script lang="ts">
import TheHeaderVue from './components/TheHeader.vue';
import watch from './components/watch.vue';
import ciclo from './components/ciclo.vue';

export default {
  name: 'App',
  components: {
    TheHeaderVue,
    watch,
    ciclo,
},
  data() {
    return {
      showAlert: true,
        user: 'isaias',
        variant: 'sucess',
        text: 'Seu formulario foi enviado',

    }
  },
  watch: {
    user: {
      handler() {
        console.log('eae')
      },
      deep: true,
    }
  },

  //hooks
  beforeCreate(){
    console.log('beforeCiado');
    console.log(this.user);
  },
  created(){
    console.log('Ciado')
  },
  beforeMount(){
    console.log('beforeMount')
  },
  mounted(){
    console.log('mounted')
  },
  beforeUnmount(){
    console.log('UnMount')
  },
  unmounted(){
    console.log('jaeraMount')

  },
  methods: {
    onClose(){
      this.showAlert = false
    }
    }
  }


</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
