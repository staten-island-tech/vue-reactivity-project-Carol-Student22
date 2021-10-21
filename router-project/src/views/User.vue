<template>
  <section class="container">
      <div class="name-container">
        <input type="text" placeholder="Game Name" class="input">
        <button class="input-btn">Change Name</button>
      </div>
  </section>
</template>

<script>
export default {
    name: "Name",
}
</script>

<style>
.container {
  display: flex;
  justify-content: center;


}
.name-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 2rem;
}

.input {
  width: 15rem;
  margin-bottom: 1rem;
  outline: none;
  border: solid 2px white;
  padding: 5px;
}


.input-btn {
  width: 9rem;
  text-decoration: none;
  border: 1.5px white solid;
}
.input-btn:hover {
    box-shadow: none;
    color: grey;
  }

</style>