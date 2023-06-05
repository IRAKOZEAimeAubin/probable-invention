<template>
  <div id="nav" class="flex gap-2 font-bold uppercase text-lg items-center justify-center p-8 text-slate-900">
    <router-link to="/">Home</router-link>
    |
    <router-link :to="{ name: 'About' }">About</router-link>
    |
    <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
  </div>
  <div class="flex items-center justify-center gap-2 font-bold mb-2">
    <button class="uppercase tracking-wide text-sm bg-red-200 p-2 rounded-md" @click="redirect">Redirect</button>
    <button class="uppercase tracking-wide text-sm bg-orange-200 p-2 rounded-md" @click="goBack">Go Back</button>
    <button class="uppercase tracking-wide text-sm bg-green-200 p-2 rounded-md" @click="goForward">Go Forward</button>
  </div>
  <router-view />
</template>

<script>
export default {
  name: "App",
  methods: {
    redirect () {
      this.$router.push( { name: "Home" } )
    },
    goBack () {
      this.$router.go( -1 )
    },
    goForward () {
      this.$router.go(1)
    }
  }
}
</script>

<style>
#nav a {
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  color: #ffffff;
  background-color: #082f49;
}
</style>