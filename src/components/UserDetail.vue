<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
    <p>User Name: <h1>   {{name}}</h1> </p>
     <p>User Age: <h1>   {{userAge}}</h1> </p>
    <button @click="resetName">ResetName</button>

    <button @click="resetFun()">ResetName</button>
    </div>
</template>

<script>
import  {eventBus} from '../main';

export default{
    props:['name','resetFun','userAge'],

    //or use below
    // props:{
    //     name:{
    //         type: String,
    //     },
    //     resetFun: Function
    // }

    methods:{
        switchName(){
            return this.name.split('').reverse().join('');
        },
        resetName(){
            this.name= "ASHU";
            this.$emit('nameWasReset',this.name)
        }
    },

    created() {
        eventBus.$on('ageWasEdited',(data)=>{
            this.userAge= data;
        });
    },

}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
