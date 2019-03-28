<template>
    <!--<div class="container">-->
        <!--<div class="row justify-content-center">-->
            <!--<div class="col-md-8">-->
                <!--<div class="card">-->
                    <!--<div class="card-header">Mahmoud Component</div>-->

                    <!--<div class="card-body">-->
                       <!--<button class="btn btn-primary" @click="counter += 1">Add 1</button>-->
                        <!--<p>you pressed {{counter}} times</p>-->
                        <!--<h3>Keyboard Events</h3>-->
                        <!--<label>Name:</label>-->
                        <!--<input type="text" class="form-control" v-model="name">-->
                        <!--<span>{{name}}</span><br>-->
                        <!--<label>Age:</label>-->
                        <!--<input type="text" class="form-control" v-model="age">-->
                        <!--<span>{{age}}</span>-->
                        <!--<h3>Computed Properties</h3>-->
                        <!--<button class="btn btn-primary" @click=" a++">Add To A</button>-->
                        <!--<button class="btn btn-primary" @click=" b++">Add To B</button>-->
                        <!--<p>A - {{a}}</p>-->
                        <!--<p>B - {{b}}</p>-->
                        <!--<p>Age + A = {{AddToA}}</p>-->
                        <!--<p>Age + B = {{AddToB}}</p>-->
                        <!--<h3>Dynamic CSS</h3>-->
                        <!--&lt;!&ndash;<div v-on:click="available = !available" v-bind:class="{available:available}">&ndash;&gt;-->
                           <!--&lt;!&ndash;<span>mahmoud</span>&ndash;&gt;-->
                        <!--<div v-bind:class="compClasses">-->
                            <!--<span>mahmoud</span>-->
                        <!--</div>-->
                        <!--<button class="btn btn-primary" @click="available= !available">Toggle available</button>-->
                        <!--<button class="btn btn-primary" @click="nearby= !nearby">Toggle nearby</button><hr>-->
                        <!--<button class="btn btn-primary" @click="error = !error">Toggle Error</button>-->
                        <!--<button class="btn btn-primary" @click="success = !success">Toggle Success</button>-->
                        <!--<p v-if="error">There has been an error!</p>-->
                        <!--<p v-else-if="success">woow, success</p><hr>-->
                        <!--<h3>Looping Through Lists</h3>-->
                        <!--<ul>-->
                            <!--<li v-for="(person, index) in persons">{{index}}.{{person}}</li>-->
                        <!--</ul>-->
                        <!--<ul>-->
                            <!--<li v-for="(developer, index) in developers">{{index}}.{{developer.name}}-{{developer.age}}</li>-->
                        <!--</ul>-->
                        <!--<template v-for="developer in developers">-->
                            <!--<div v-for="(value,key ) in developer">-->
                                <!--<p>{{key}}:{{value}}</p>-->
                            <!--</div>-->
                        <!--</template>-->
                        <!--</div>-->
                    <!--</div>-->
                <!--</div>-->
            <!--</div>-->
        <!--</div>-->

<div class="container">
    <nav class="navbar navbar-expand-md navbar-light navbar-laravel">
        <div class="container">
                <!-- Left Side Of Navbar -->
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item" v-for="developer in developers">
                        <a class="nav-link" href="#">{{ developer }}</a>
                    </li>
                </ul>
            </div>
    </nav><br>
    <h1>Mahmoud Component</h1>
    <example-component></example-component><br>
    <!-- bag image -->
    <div id="bag">
       <img :src="getphoto" alt="ff" width="200px" height="200px" v-show="!ended"/>
        <img :src="getphoto2" alt="fff" width="200px" height="200px" v-show="ended" />
    </div>
    <!--bag health-->
    <div id="bag-health">
        <div v-bind:style="{width: health + '%'}"></div>
    </div>
    <!--game controls-->
    <div id="controls">
        <button @click="punch" v-show="!ended" class="btn btn-danger">Punch</button>
        <button @click="restart" class="btn btn-success">Restart</button>
    </div><br><hr>
    <div>{{name}}</div>
    <button @click="ToggleName" class="btn btn-info">Toggle Name</button>
</div>
</template>

<script>
    export default {
       // data(){
       //     return {
       //         counter:0,
       //         name: '',
       //         age: '',
       //         a: 0,
       //         b: 0,
       //         Age: 20,
       //         available: false,
       //         nearby: false,
       //         error: true,
       //         success: true,
       //         persons:['mahmoud', 'ahmed', 'nour'],
       //         developers:[
       //             {name:'mahmoud', age:23},
       //             {name:'ahmed', age:22},
       //             {name:'nour', age:21}
       //         ]
       //     }
       // },
       //  mounted(){
       //      console.log("worked");
       //  },
       //  computed:{
       //      AddToA: function () {
       //          console.log("AddToA");
       //          return this.Age + this.a ;
       //      },
       //      AddToB: function () {
       //          console.log("AddToB");
       //          return this.Age + this.b ;
       //      },
       //      compClasses:function () {
       //          return {
       //              available: this.available,
       //              nearby: this.nearby
       //          }
       //      }
       //  }
        data: function(){
            return{
                photo: 'bag.jpg',
                health: 100,
                ended: false,
                photo2: 'bag-burst.jpg',
                name: 'mahmoud',
                developers:['mahmoud', 'nour', 'ahmed']
            }
        },
        methods:{
            punch:function () {
                this.health -=10 ;
                if(this.health <= 0){
                    this.ended =true ;
                }
            },
            restart:function(){
                this.health = 100 ;
                this.ended = false ;
            },
            ToggleName:function () {
                if(this.name == 'mahmoud') {
                    return this.name = 'Sayed';
                }
                else {return this.name = 'mahmoud'; }
            }

        },
        computed:{
            getphoto(){
                return "img/"+ this.photo ;
            },
            getphoto2(){
                return "img/"+ this.photo2 ;
            }
        }
    }
</script>

<style scoped>
    /*span{*/
        /*background: red;*/
        /*display: inline-block;*/
        /*padding: 10px;*/
        /*color: #fff;*/
        /*margin: 10px 0;*/
    /*}*/
    /*.available span{*/
        /*background: green;*/
    /*}*/
    /*.nearby span:after{*/
        /*content: "nearby";*/
        /*margin-left: 10px;*/
    /*}*/

    #bag{
        width: 200px;
        height: 300px;
    }
    #bag-health{
        width:200px;
        border: 2px solid #000;
    }
    #bag-health div{
        height: 20px;
        background: crimson;
    }
    #controls{
        margin-top: 20px;
        margin-left: 30px;
    }
    h1{
        color: rebeccapurple;
    }


</style>