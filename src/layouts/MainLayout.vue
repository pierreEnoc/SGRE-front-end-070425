<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />

        <q-toolbar-title> SGRE - Sistema Gerenciador de Rede Elétricas </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Menu </q-item-label>

        <EssentialLink v-for="link in linksList" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Gerenciar Rede',
    caption: 'Gerenciar Rede Elericas',
    icon: 'electric_bolt',
    link: 'https://quasar.dev',
  },
  {
    title: 'Gerencir Subestacao',
    caption: 'Gerenciar Sub Estacoes',
    icon: 'cable',
    link: 'https://github.com/quasarframework',
    disable: true,
  },
  {
    title: 'Gerenciar Acessos',
    caption: 'Gerenciar usuarios e perfils',
    icon: 'manage_accounts',
    link: 'https://chat.quasar.dev',
    disable: true,
  },
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
