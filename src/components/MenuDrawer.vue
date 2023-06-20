<template>
    <q-tabs align="justify"  :vertical="isVertical" :class="isVertical ? 'custom-center' : ''">
            <q-route-tab to="/" label="Home" icon="home" />
            <q-route-tab to="/repairs" label="Repairs" icon="build" />
            <q-route-tab to="/shop" label="Shop" icon="shop" />
            <q-route-tab to="/about" label="About Us" icon="groups" />
            <q-route-tab to="/contact" label="Contact" icon="email" />
    </q-tabs>
</template>

<script setup lang="ts">
import { useQuasar } from 'quasar';

const $q = useQuasar()

defineProps<{
    isVertical: boolean
}>()

</script>

<style lang="scss" scoped>
    .custom-center {
        top: 50%;
        transform: translateY(-25%);
    }
</style>