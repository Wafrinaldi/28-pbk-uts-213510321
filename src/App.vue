<template>
  <div id="nav" class="navbar">
    <h1>VUE ROUTER</h1>
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About</router-link></li>
      <li><router-link to="/todo">Todo List</router-link></li>
    </ul>
  </div>
  <router-view />
</template>

<style>
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: white;
}

#nav a.router-link-exact-active {
  color: black;
  background: crimson;
  border-radius: 10px;
}
</style>
