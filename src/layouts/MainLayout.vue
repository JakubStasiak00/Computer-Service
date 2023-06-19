
<template>
  <q-layout view="hHr lpr ffr">

    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar :class="$q.screen.lt.sm ? 'q-px-xs' : 'q-px-md'">
        <q-toolbar-title class="flex items-center text-h5">
          <q-avatar>
            <q-icon name="construction" size="md"/>
          </q-avatar>
          <span class="text-accent text-bold">Bluebear</span>Service
        </q-toolbar-title>

        <q-btn dense flat icon="menu" @click="toggleRightDrawer" size="lg" v-if="$q.screen.lt.sm"/>
      </q-toolbar>

      <MenuDrawer v-if="$q.screen.gt.xs" :is-vertical="false" />
    </q-header>

    <q-drawer v-model="rightDrawerOpen" side="right" overlay bordered v-if="$q.screen.lt.sm">
      <MenuDrawer :is-vertical="true" />
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal class="bg-grey-8 text-white">
      <q-toolbar>
        Copyright placeholder
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