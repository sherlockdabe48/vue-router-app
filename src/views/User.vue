<template>
    <div>
        <h1>Welcome, {{ user }}</h1>
        <p>
        <router-link :to="{ name: 'Invoices' }">Invoices</router-link>
        </p>
        <button @click="logout" class="btn">Logout</button>
    </div>
</template>

<script>
import store from '@/store'
    export default {
        data() {
            return {
                user: store.user
            }
        },
        methods: {
            logout() {
                store.user = null
                this.$router.push("/")
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>