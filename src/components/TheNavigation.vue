<template>
    <div id="nav">
        <router-link to="/" class="logo">
                LOGO HERE
        </router-link>
        
            <ul class="nav-links">
                <li 
                v-for="destination in destinations" 
                :key="destination.name"
                >
                    <router-link :to="{
                        name: 'DestinationDetails',
                        params: {slug: destination.slug}
                        }" class="link">
                    {{ destination.name }}
                    </router-link>
                </li>
                <li class="links">
                    <router-link to="/user">Dashboard</router-link>
                </li>
            </ul>
    </div>
</template>

<script>
import store from '@/store'
    export default {
        data() {
            return {
                destinations: store.destinations,
            }
        },
    }
</script>

<style scoped>

#nav {
  display: flex;
  justify-content: space-between;
  align-items: center ;
  position: sticky;
  top: 0;
  z-index: 1;
  background-color: white;
  border-bottom: 1px solid grey;
margin-bottom: 10px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 10px;
  text-decoration: none;
  font-weight: bold;
 
}

#nav a.router-link-exact-active {
  color: #42b983;
}


.nav-links {
    display: flex;
    list-style: none;
}

.link {
    padding-right: 20px;
    text-align: center;
    align-items: center;
    justify-content: center;
}

#nav ul a:hover {
    color: white;
}
.link:hover {
    background-color: #42b983;
}

.logo {
    color: black;
    font-size: large;
    text-decoration: none;
}
</style>