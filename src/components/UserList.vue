<template>
    <div>
        <p>User List</p>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eos, numquam? Repellat exercitationem delectus facilis quibusdam nesciunt, quia officiis libero assumenda! Suscipit illum repudiandae ducimus sunt ullam! Nostrum iure impedit commodi?</p>
    </div>
    <div v-if="loading">
        <Spinner />
    </div>
    <div v-if="!loading && users.length > 0">
        <table>
            <thead>
                <tr>
                    <th>Serial Number</th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Company</th>
                    <th>Website</th>
                    <th>Location</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in users" :key="user.id">
                    <td>{{user.id}}</td>
                    <td>{{user.name}}</td>
                    <td>{{user.email}}</td>
                    <td>{{user.company.name}}</td>
                    <td>{{user.website}}</td>
                    <td>{{user.address.city}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import {UserService} from "@/services/UserService.js";
import Spinner from "@/components/Spinner.vue"

export default {
    name : "UserList",
    components : {
        Spinner
    },
    data : function() {
        return {
            loading : false,
            users : [],
            errorMessage : null
        }
    },
    created : async function() {
        try {
            this.loading = true;
            let response = await UserService.getAllUsers();
            this.loading = false;
            this.users = response.data;
        } catch (error) {
            this.loading = false;
            this.errorMessage = error;
        }

    }
}
</script>

<style scoped>

</style>
