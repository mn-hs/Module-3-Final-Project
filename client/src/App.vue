<template>
  <div id="app">
    <header>
      <img src="https://via.placeholder.com/700x200.jpg">
      <nav>
        <router-link class="router-link-exact-active link" v-bind:to="{name: 'home'}">Home</router-link>
        <router-link class="router-link-exact-active link" v-bind:to="{name: 'cart'}" exact>Cart</router-link>
        <router-link class="link" v-bind:to="{ name: 'logout' }" v-if="$store.state.token" exact>Logout</router-link>
        <router-link class="router-link-exact-active link" v-bind:to="{ name: 'login' }" v-else exact>Login</router-link>
      </nav>
      <span class="banner"><p>{{ this.$store.state.messageBanner }}</p></span>
    </header>
    <main>
      <router-view />
    </main>
    <footer>
      <p>© 2022 All rights reserved.</p>
    </footer>
  </div>
</template>


<style scoped>
  #app{
    display: flex;
    flex-direction: column;
    justify-content: center;
    border: 0.25px solid black;
    width: 100%;
    height: 100%;
  }

  header{
    background-color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-bottom: 0.25px solid black;
    position: sticky;
    top: 0;
    z-index: 999;
  }
  header > img {
    width: 100%;
    height: 200px;
    border-bottom: 0.25px solid black;
  }
  header > nav{
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 99%;
    gap: 20px;
    /* border-top: 0.25px solid black; */
    padding: 8px;
  }
  .link{
    text-decoration: none;
    font-weight: 700;
    margin: 8px;
  }
  header > nav .link:last-child{
    margin-left: auto;
  }

  header > span.banner{
    display: block;
  }

  main{
    padding: 8px;
  }

  footer{
    background-color: white;
    padding: 8px;
    border-top: 0.25px solid black;
    position: sticky;
    bottom: 0;
  }
  footer > p{
    margin: 0px;
  }
</style>