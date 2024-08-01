<template>
    <div>
        <h1> Attractions </h1>
        <li v-for="i in items">
            {{ i.name }}
            <br/>
            <img :src="i.coverimage"/>
            <br/>
            <nuxt-link :to="'/attraction/'+i.id">
                like to know more?
            </nuxt-link>
            <br/>
        </li>
    </div>
</template>

<script setup>
import {ref} from 'vue';
const items = ref([])

fetch('https://www.melivecode.com/api/attractions')
    .then(res => res.json())
    .then((result) =>{
        items.value = result
        console.log(result)
    })
</script>