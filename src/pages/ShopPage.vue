<template>
    <h2 class="text-center text-h4 text-bold text-primary">Explore our shops' amazing assortiment</h2>
    <div class="flex justify-around" :class="$q.screen.lt.sm ? 'wrap' : 'no-wrap'">
        <q-input outlined class="q-pa-md" v-model="name" label="Search By Name" style="min-width: 300px; width: 100%;" />
        <q-select outlined v-model="sortBy" :options="options" label="Sort By" class="q-pa-md" style="min-width: 300px; width: 100%;" />
    </div>

    <div class="row justify-evenly q-ma-md q-gutter-md">
        <q-card v-for="product in products" :key="product.id" class="q-pa-md">
            <div class="text-h5 text-bold" style="max-width: 300px; min-height:95px;">
                {{ product.name }}
            </div>

            <q-img src="../images/dummy-pc.webp" v-if="product.rating === 5" />
            <q-img src="../images/dummy-mid.webp" v-else-if="product.rating === 4" />
            <q-img src="../images/dummy-worse.webp" v-else />

            <div class="flex items-center">
                <span class="text-subtitle1 text-bold">Performance Score:</span><q-rating class="q-pa-md"
                    v-model="product.rating" max="5" size="sm" icon="build" readonly color="accent" />
            </div>
            <div><span class="text-bold">System:</span> {{ product.system }} </div>
            <div><span class="text-bold">Processor:</span> {{ product.processor }} </div>
            <div><span class="text-bold">GPU:</span> {{ product.gpu }} </div>
            <div><span class="text-bold">RAM:</span> {{ product.ram }} </div>
            <div class="text-right text-h6 text-bold">{{ product.price }} &#36</div>
        </q-card>
    </div>
</template>

<script setup lang="ts">
import shopData from '../jsonData/shopItems.json'
import { ref } from 'vue';
import { useQuasar } from 'quasar';

const $q = useQuasar()
const products = ref([...shopData])
const sortBy = ref(null)
const options = ['score', 'price', 'name']
const name = ref('')

</script>