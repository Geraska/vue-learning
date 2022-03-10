<template>
    <p>{{ count }}</p>
    <button class="incr" @click="incr()">Increment</button>
    <button class="decr" @click="decr()">Decrement</button>
</template>

<script>
export default {
    name : "Counter",
    data : function() {
        return {
            count : 0
        };
    },
    methods : {
        incr : function() {
            this.count += 1
        },
        decr : function() {
            this.count -= 1
        }
    }
};
</script>
