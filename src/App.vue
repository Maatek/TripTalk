<template>
  <div v-if="showApp">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <img alt="logo" src="./assets/TRIPlogo.jpg" class="jpg">

      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/home">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/profile">My Profile</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/login" @click="logout">Logout</router-link>
          </li>
        </ul>
      </div>
    </nav>
  
    <router-view/>
    <div v-if="showLogoutMessage" class="alert alert-success" role="alert">
      Successful logout!
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      showApp: true,
      showLogoutMessage: false
    }
  },
  beforeRouteEnter(to, from, next) {
    next(vm => {
      vm.showApp = !to.meta.hideApp;
    });
  },
  methods: {
    logout() {
      // Perform logout actions here
      // For the example, we'll just show the success message
      this.showLogoutMessage = true;
      
      // Hide the success message after 3 seconds
      setTimeout(() => {
        this.showLogoutMessage = false;
      }, 3000);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.jpg {
  width: 5%;
  margin-left: 3px;
}
</style>
