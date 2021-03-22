<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/search">
        <div class="menu-item search">
          <img src="/images/search.png">
        </div>
      </router-link>
      <router-link to="/donations">
        <div class="menu-item">
          <img src="/images/donate.png">
          <p>${{donationSum}}</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>

<script>
export default {
  computed: {
    donationSum() {
      return (this.$root.$data.donations.length * 5);
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: Optima;
  font-weight: 700;
}

body {
  /* margin: 50px 100px;
  width: 90%; */
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
  background-color: #bcccc0;
  padding: 10px;
  width: 100vw;
}

#menu a {
  color: black;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
  display: flex;
  justify-content: center;

}

.search {
  margin-right: 50px;
}
</style>
