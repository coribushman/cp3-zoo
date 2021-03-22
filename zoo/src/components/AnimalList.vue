<template>
<div class="wrapper">
  <div class="animals">
    <div class="animal" v-for="animal in animals" :key="animal.id">
      <div class="image">
        <img :src="animal.image">
      </div>
      <div class="info">
        <h1>{{getAnimalType(animal)}}</h1>
        <p>Scientific Name: {{animal.scientific.toLowerCase()}}</p>
        <p>Name: {{animal.first_name}}</p>
        <p>Gender: {{animal.gender}}</p>
        <p>Origin: {{animal.origin_country}}</p>
        <p>Age: {{animal.age}}</p>
      </div>
      <div class="donate-button">
        <button class="auto" v-on:click="addToDonations(animal)">Donate $5</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
  export default {
  name: 'AnimalList',
  props: {
    animals: Array
  },
  methods: {
    addToDonations(animal){
      this.$root.$data.donations.push(animal);
    },
    getAnimalType(animal) {
      let str = animal.type;
      if (str.includes(",")) {
        let array = str.split(",");
        let first = array.shift();
        array.push(first);
        str=array.join(" ");
      }
      return str.toLowerCase();
    }
  }
}
</script>


<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.animals {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

/* .animal {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
  padding: 10px;
}

.animal img {
  border: 2px solid #333;
  height: 200px;
  width: 250px;
  /* object-fit: cover;
  object-fit: fill;
}

.animal .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
} */
.animal {
  display: flex;
  flex-direction: column;
  justify-contents: center;
  align-items: center;
  background-color: #e3e3e3;
  padding: 10px;
  margin-bottom: 20px;
  width: 400px;
}

.animal img {
  border: 2px solid #333;
  height: 200px;
  /* width: 250px; */
  /* object-fit: cover; */
  object-fit: contain;
}

/* .info {
  background: #F2921D;
  color: #000;
  padding: 10px 30px;
  height: 80px;
} */

.info {
  margin: 10px;
}

.info h1 {
  font-size: 25px;
  text-transform: capitalize;
}

.info p {
  margin: 0px;
  font-size: 15px;
}


button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
