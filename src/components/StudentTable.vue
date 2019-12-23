<template>
<div class="user">
<h1>{{user.name}}</h1>
</div>
</template>

<script>
export default {
    name: 'User',
    data() {
        return {
        user:{
            name:'Brad'
        }
    }
}
}
</script>

<style scoped>
    h1{
        font-size:2rem;
    }
</style>
