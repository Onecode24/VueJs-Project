<template>
    <div class="cards">
        <h2>{{title}}</h2>
        <hr>
        <div class="foot">
            <pre>likes: {{likes}}</pre>
            <pre>updated: {{isUpdated ? 'Yes' : 'No'}}</pre>
        </div>
    </div>
</template>

<script>
    export default {
     name: 'Article-cards',
     props:{
        title: {
            type: String,
            required: true,
            default: 'No title'
        },
        likes: {
            type: Number,
            required: true,
            default: 0
        },
        isUpdated: Boolean ,
     }   
    }
    
</script>

<style>
    .cards{
        background-color: #f5f5f5;
        padding: 20px;
        border-radius: 50px;
        margin-bottom: 20px;
        border: gray solid 1px;
        width: 30%;
        margin-left: 35%;
    }
    .foot{
        display: flex;
        justify-content: space-around;
    }
</style>