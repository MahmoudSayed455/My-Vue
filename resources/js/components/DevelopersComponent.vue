<template>
    <div id="developers">
        <ul>
            <li v-for="developer in developers" @click="developer.show  = !developer.show">
               <h2> {{developer.name}}</h2>
               <h3 v-show="developer.show"> {{developer.speciality}}</h3>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                developers:[
                    {name:'mahmoud', speciality:'Htmltags', show:false},
                    {name:'nour', speciality:'Csstags', show:false},
                    {name:'ahmed', speciality:'Javatags', show:false},
                    {name:'mohamed', speciality:'Phptags', show:false},
                    {name:'ali', speciality:'pytontags', show:false},
                    {name:'omar', speciality:'linuxtags', show:false}
                ]
            }
        }
    }
</script>

<style scoped>
    #developers{
        width: 100%;
        max-width: 1200px;
        margin: 40px auto;
        padding: 0 20px;
        box-sizing: border-box;
    }
    ul{
        display: flex;
        flex-wrap: wrap;
        list-style-type: none;
        padding: 0;
    }
    li{
        flex-grow: 1;
        flex-basis: 300px;
        text-align: center;
        padding: 20px;
        border: 1px solid #222;
        margin: 10px;
    }

</style>