<template>
    <footer>
        <p> {{copyright}} </p>
    </footer>
</template>

<script>
    export default {
        name: "FooterComponent",
        data(){
            return{
                copyright:'copyrights for mahmoud sayed 2019'
            }
        }
    }
</script>

<style scoped>
    footer{
        background: #222;
        padding: 10px;
    }
    p{
        color: lightgreen;
        text-align: center;
    }

</style>