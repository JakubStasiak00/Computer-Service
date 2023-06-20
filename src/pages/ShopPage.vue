<template>
    <h2 class="q-mx-auto q-px-lg text-h4 text-center text-bold" style="max-width: 1100px;"> Please explore our impressive range of state-of-the-art personal computers, showcasing the latest advancements in technology. We offer the convenience of allowing you to preview these exceptional products before making your in-store purchase. </h2>
    <div class="row justify-evenly q-ma-md q-gutter-md">
        <q-card v-for="product in products" :key="product.id" class="q-pa-md">
            <div class="text-h5 text-bold" style="max-width: 300px; min-height:95px;"> 
                {{ product.name }}
            </div>

            <q-img src="../images/dummy-pc.webp" v-if="product.rating === 5" />
            <q-img src="../images/dummy-mid.webp" v-else-if="product.rating === 4" />
            <q-img src="../images/dummy-worse.webp" v-else />

            <div class="flex items-center">
                <span class="text-subtitle1 text-bold">Performance Score:</span><q-rating class="q-pa-md" v-model="product.rating" max="5" size="sm" icon="build" readonly color="accent" />
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

    const products = ref([...shopData])

</script>