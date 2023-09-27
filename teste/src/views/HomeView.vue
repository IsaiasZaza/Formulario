<template>
    <div>
        <theHeaderVue v-if="showHeader" />

        <div v-show="showName">
            Nome: {{ name }}
            SobreNome {{ sobreName }}
        </div>
        <div v-if="acessLevel === 'admin'">Admin</div>
        <div v-else-if="acessLevel === 'User'">User</div>
        <div v-else>Usuário normal</div>
        <header>
            <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
        </header>
    </div>
</template>


<script lang="ts">
import theHeaderVue from '@/components/TheHeader.vue';
import { defineComponent } from 'vue';
export default{
    data() {
        return {
            theHeaderVue,
            showHeader: true,
            name: 'Jon Snow',
            sobreName: 'Targheryan',
            showName: false,
            acessLevel: 'admin'
        }
    }
}


</script>

<style></style>