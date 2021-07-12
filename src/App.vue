<template>
  <div id="app">
    <TheNavigation />
    <transition name="slide" mode="out-in">
    <router-view :key="$route.path" />
    </transition>
  </div>
</template>

<script>
export default {
  components: {
      TheNavigation: () => import(/* webpackChunkName: "navigation-bar" */ '@/components/TheNavigation.vue')
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.5s, transform 0.5s;
}

.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(5%);
}

.moveUp-enter-active {
  animation: fadeIn 0.75s ease-in
}

@keyframes fadeIn {
  0% {
    opacity: 0
  }

  50% {
    opacity: 0.5
  }

  100% {
    opacity: 1
  }
}

.moveUp-leave-active {
  animation: moveUp 0.3s ease-in
}

@keyframes moveUp {
  0% {
    transform: translateY(0)
  }
  100% {
    transform: translateY(-400px);
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.input {
  border: 1px solid green;
  padding: 10px;
  margin-bottom: 20px;
}

.btn {
  background-color: green;
  color: white;
  padding: 10px;
}

</style>
