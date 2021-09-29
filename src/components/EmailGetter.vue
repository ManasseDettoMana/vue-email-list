<template>
    <div class="email-getter">
        <ul>
            <li v-for="(element, index) in emailList" :key="index">{{element}}</li> 
        </ul>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'EmailGetter',
    data: function(){
        return{
            emailList : []
        }
    },
    mounted(){
        for(let i=0;i<10;i++){
            axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
                .then( (response) => { 
                    this.emailList.push(response.data.response);
                })
        }
    }

}
</script>

<style>

</style>