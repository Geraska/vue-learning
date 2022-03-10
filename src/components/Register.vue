<template>
    <div>
        <p>Register Here</p>
    </div>
    <form @submit.prevent="register()">
        <div>
            <input v-model="user.name" type="text" placeholder="Name">
        </div>
        <div>
            <input v-model="user.email" type="email" placeholder="Email">
        </div>
        <div>
            <input v-model="user.password" type="password" placeholder="Password">
        </div>
        <div>
            <input type="submit" value="Register">
        </div>
    </form>
</template>

<script>
export default {
    name : "Register",
    data : function() {
        return {
            user : {
                name: "",
                email: "",
                password: ""
            }
        }
    },
    methods : {
        register : function() {
            console.log(this.user);
        }
    }
}
</script>

<style scoped>

</style>