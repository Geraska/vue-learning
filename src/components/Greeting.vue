<template>
    <h2>Good {{this.msg}}</h2>
    <button @click="greet('Morning')">Morning</button>
    <button @click="greet('Afternoon')">Afternoon</button>
    <button @click="greet('Evening')">Evening</button>
</template>

<script>

export default {
    name: "Greeting",
    data : function() {
        return {
            msg: ""
        }
    },
    methods : {
        greet : function(value) {
            this.msg = value;
        }
    }
}
</script>

<style scoped>

</style>
