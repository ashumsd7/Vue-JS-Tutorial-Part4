<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <hr>
       <p>Name is in User Vue :<h4>{{name}}</h4></p>
         <p>Age is in User Vue :<h4>{{age}}</h4></p>
       



        <button @click=changeName>Chnage My name</button>



        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :name="name"
                                @nameWasReset="name=$event"
                                :resetFun="resetName"
                                :userAge="age"
                               
                >


                </app-user-detail>
            </div>



            <div class="col-xs-12 col-sm-6">
                <app-user-edit
                    :userAge="age"
                     @ageWasEdited="age=$event"
                ></app-user-edit>
            </div>
        </div>
    </div>




</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {

        data(){
            return{
                name : "ASHU",
                age:27
            }

        },
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        },

        methods:{
            changeName(){

                this.name= "AASIM";
                
            },

            resetName(){
                this.name= "ASHU"
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
