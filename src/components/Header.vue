<template>
    <header>
        <h1>{{title}}</h1>
        <Button @click="onClick()" text="Add Task" color="green" />
    </header>
</template>
<script>
import Button from './Button';
export default {
    name:'Header',
    props:{
        title:String,
    },
    methods : {
        onClick() {
           
            console.log('Clicked');
        }
    },
    components:{Button}
}
</script>
<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>