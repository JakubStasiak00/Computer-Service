
<template>
  <q-layout view="hHr lpr ffr">

    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar :class="$q.screen.lt.sm ? 'q-px-xs' : 'q-px-md'">
        <q-toolbar-title class="flex items-center text-h5">
          <q-avatar>
            <q-icon name="construction" size="md"/>
          </q-avatar>
          BluebearService
        </q-toolbar-title>

        <q-btn dense flat icon="menu" @click="toggleRightDrawer" size="lg" v-if="$q.screen.lt.sm"/>
      </q-toolbar>

      <MenuDrawer v-if="$q.screen.gt.xs" />
    </q-header>

    <q-drawer v-model="rightDrawerOpen" side="right" overlay bordered>
      <MenuDrawer />
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          <div>Title</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import MenuDrawer from '../components/MenuDrawer.vue'
import { useQuasar } from 'quasar';

    const $q = useQuasar()

    const rightDrawerOpen = ref(false)

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

</script>