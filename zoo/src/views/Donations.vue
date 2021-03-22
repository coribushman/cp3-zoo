<template>
<div class="wrapper">
  <div class="donations">
    <div class="animal" v-for="animal in this.$root.$data.donations" :key="animal.id">
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
      <div class="button">
        <button class="remove" v-on:click="removeDonations(animal)">Remove animal's donations</button>
      </div>
    </div>
  </div>
  <div class="empty" v-if="this.$root.$data.donations.length === 0">You have not made any donations</div>
  <div class="footer">
    <a href='https://github.com/coribushman/cp3-zoo'>Github</a>
  </div>
</div>
</template>

<script>
export default {
  name: 'Donations',
  methods: {
    removeDonations(animalToRemove){
      this.$root.$data.donations = this.$root.$data.donations.filter(animal =>
        animal !== animalToRemove);

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
.empty {
  display: flex;
  justify-content: center;
  padding-bottom: 400px;
}

.donations {
  display: flex;
  flex-direction: column;
  justify-contents: center;
  align-items: center;
}

.animal {
  display: flex;
  flex-direction: column;
  justify-contents: center;
  align-items: center;
  background-color: #e3e3e3;
  padding: 10px;
  margin-bottom: 20px;
  width: 400px;
  text-transform: capitalize;
}

.animal img {
  border: 2px solid #333;
  height: 200px;
  width: 250px;
  /* object-fit: cover; */
  object-fit: fill;
}

.footer {
  display: flex;
  justify-content: center;
  padding: 20px;
  bottom: 0;
  left: 41%;
  background-color: #bcccc0;
}
</style>
