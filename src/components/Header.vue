<template>
    <header>
        <h1>{{title}}</h1>
        <ButtonComponent text="klik"></ButtonComponent>
    </header>
</template>

<script>

import ButtonComponent from './Button'

    export default {
        name: 'HeaderComponent', 
        props: {
            title: String,
        }, 
        components:{
            ButtonComponent,
        },
    }
        
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>