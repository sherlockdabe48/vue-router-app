<template>
    <div>
        <span class="go-back">
            <button @click="goBack">Go Back</button>
        </span>
    </div>
</template>

<script>
    export default {
        methods: {
            goBack() {
                return this.$router.go(-1) 
            }
        },
    }
</script>

<style  scoped>

.go-back {
    display: flex;
}

button {
    cursor: pointer;
    color: white;
    border: none;
    border-radius: 10px;
    padding: 4px 10px ;
    background-color: cadetblue;
    
}
</style>