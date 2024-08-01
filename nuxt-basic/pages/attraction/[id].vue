<template>
    <div>
        <!--h1>{{ items }}</h1-->
        <h1>{{ items.name }}</h1>
        <img :src=" items.coverimage">
        <p>{{ items.detail }}</p>
    </div>
</template>

<script setup>
import {ref} from 'vue'
const routes = useRoute()
const items = ref({})
const id = routes.params.id

console.log(routes.params.id)
fetch('https://www.melivecode.com/api/attractions/'+id)
    .then(res => res.json())
    .then((result) =>{
        items.value = result.attraction
    })
</script>
