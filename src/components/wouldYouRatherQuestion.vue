<template>
<div>
    <div class="container"
         v-for=" i in questions" :key="i.id">         
        <h2> {{ i.question }}</h2>
        <input id=button name="i.id" type="radio" v-model= "choice" v-bind:value="i.answer1+','+i.id"  v-on:change="$emit('answer-changed', choice)">        
         <label> {{ i.answer1 }}</label>
         <input id=button  name=i.id type="radio" v-model= "choice" v-bind:value="i.answer2+','+i.id" v-on:change="$emit('answer-changed', choice)">
         <label> {{ i.answer2 }}</label>         
    </div>

</div>
</template>

<script>
export default {
    name:'wouldYouRatherQuestion',
props:{
    questions: Array
},
    data() {
        return {
            choice:""
        }
    },
} 
</script>

<style>
body{
    background-color: rgb(218, 181, 221);
}
.container {
    background-color: rgb(209, 181, 236);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    text-align:  center;
    font-size: 20px;

}
#button{
    font-family: 'Times New Roman', Times, serif;
}

</style>


