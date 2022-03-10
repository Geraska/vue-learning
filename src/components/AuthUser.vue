<template>
    <div v-if="isLoggedIn">
        <p class="greeting">Wlecome User!</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Labore modi quisquam ipsum mollitia laborum, quas ea adipisci sunt sapiente odio illo nulla voluptas omnis? Odio quas iure non sunt dicta.</p>
    </div>
    <div v-if="!isLoggedIn">
        <p class="not-greeting">Thank You!</p>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Numquam eligendi sunt vero esse quaerat ullam tempore harum, iste eaque magni sed nam culpa, ipsum, unde sint ratione voluptas facere provident.</p>
    </div>
    <div>
        <button v-if="!isLoggedIn" class="login" @click="login()">Login</button>
        <button v-if="isLoggedIn" class="logout" @click="logout()">Logout</button>
    </div>
</template>

<script>
export default {
    name : "AuthUser",
    data : function() {
        return {
            isLoggedIn: false
        };
    },
    methods : {
        login : function() {
            this.isLoggedIn = true;
        },
        logout : function() {
            this.isLoggedIn = false;
        }
    }
}
</script>

<style scoped>
    p {
        margin: 20px;
    }
    .greeting {
        color: blue;
        font-size: 30px;
    }
    .not-greeting {
        color: red;
        font-size: 30px;
    }
    button {
        border: .1px;
        border-radius: 1px;
    }
    .login {
        background-color: green;
        color: white;
    }
    .logout {
        background-color: pink;
        color: black;
    }
</style>