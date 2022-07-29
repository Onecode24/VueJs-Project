<template>
    <div>
        <h2 v-if="time<=12">Good Morning, {{name}}</h2>
        <h1 v-else>Good Afternoon</h1>
        <pre>{{pseudo}}</pre>
    </div>
</template>

<script>
    export default {
        name: 'Greet-world',
        props: ['name', 'pseudo'],
        data(){
            return{
                msg: 'Good Morning World',
                time: 10,
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>