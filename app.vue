<template>
    <div id="ap">
        <div class="container">

            <div class="col-lg-8 m-auto d-block">
                <h1>{{title}}</h1>
                <form>
                    <div class="form group">
                        <input type="text" name="FontColor" class="form-control" id="hex" placeholder="Hex">
                    </div>
                    <br>
                    <div class="col m6">
                        <div class="box card z-depth-4" v-bind:style = '{backgroundColor:colorBoxVal}'>

                        </div>
                    </div>
                </form>
            </div>
        </div>

    </div>
</template>

<script lang="js">
    import Vue from 'vue';

    new Vue({
        data: {
            title: 'Font Color: ',
            return : {
                opacity: 50
            }
                } ,

        methods: {
            convertHex: function (color) {
                color = color.replace('#', '')
                let r = parseInt(color.substring(0, 2), 16)
                let g = parseInt(color.substring(2, 4), 16)
                let b = parseInt(color.substring(4, 6), 16)
                let result = 'rgba(' + r + ',' + g + ',' + b + ',' + this.opacity / 100 + ')'
                return result
            }
        },
        computed:{
            colorBoxVal:function(){
                return "rgb("+this.r+","+this.g+","+this.b+")"

            }
        }

    })
</script>

<style scoped>
    .app{
        margin-top: 50px;
    }
    .box{
        width: 100%;
        height:300px;
    }
</style>