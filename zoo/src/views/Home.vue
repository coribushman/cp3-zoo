<template>
<div class="page">
  <div class="main">
    <h1>Come Visit Nally Zoo</h1>
    <div class="items">
      <p>Family fun for everyone!</p>
      <img src="https://www.gannett-cdn.com/media/2019/08/12/USATODAY/usatsports/gettyimages-474690025.jpg?width=2560" alt="zoo">
      <router-link class="link" to="/search">Learn about our wonderful animals</router-link>
      <router-link class="link" to="/donations">Make a donation</router-link>
    </div>
  </div>
  <div class="footer">
    <a href='https://github.com/coribushman/cp3-zoo'>Github Classroom</a>
  </div>
</div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style scoped>
  .page {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .main{
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .items{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    font-size: 50px;
    padding: 20px;
  }

  .link {
    margin: 20px;
  }


  h1 {
    display: flex;
    font-size: 70px;
  }

  img {
    width: 50%;
    margin: 20px;
  }

  .footer {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    bottom: 0;
    left: 41%;
    background-color: #bcccc0;
    align-items: center;
    padding: 10px;
    width: 100%;
  }
</style>
