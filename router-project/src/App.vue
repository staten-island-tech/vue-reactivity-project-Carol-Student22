<template>
  <section id="app">


    <div id="nav">
      <router-link to="/">Return to Store</router-link> |
      <router-link to="/user">Change Name</router-link>
    </div>
    <router-view/>


  </section>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
* {
    font-family: 'VT323', monospace;
    font-size: 1.5rem;
    color: white;

    background: black;
}
@media screen and (max-width: 900px) {
  * {
    font-size: 1.25rem;
  }
}


</style>
