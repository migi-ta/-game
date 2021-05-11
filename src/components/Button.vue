<template>
    <p>
        <button @click.once="reset">リセット</button>
    </p>
</template>

<script>
export default {
    methods: {
        reset: function(){
            let btn = document.getElementsByTagName('button');
            console.log(btn);
        }
        
    }
    
}


</script>

<style scoped>
button{
    background-color: aquamarine;
}
</style>

