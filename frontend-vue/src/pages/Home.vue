<template>
    <div class="container">
        <h1>Home Page</h1>
        <h3>{{ user?.name }}</h3>
        <h3>{{ user?.email }}</h3>
    </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios'

const user = ref();

onMounted(async()=>{
    const data = await axios.get('/api/user');
    console.log(data)
    user.value = data.data;
})
</script>