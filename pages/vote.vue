<template>
  <div>
    <h2>vote for the cat</h2>
    <div class="row">
      <div class="col candidate">
        <img v-bind:src='catRight' class="img-fluid float-right acat" alt="Responsive cat">
<!--        add button-->
      </div>
      <div class="col candidate">
        <img v-bind:src='catLeft' class="img-fluid float-left acat" alt="Responsive cat">
      </div>
    </div>
  </div>

</template>

<script>
  import initCats from '~/assets/cats.json';

  let cats = initCats;
  let scores = {};



export default {
  name: 'PageVote',
  data() {
    return {
      catLeft: catLeft.url,
      catRight: catRight.url
    }
  }
}

const newCat = function(remove) {
  const cat = cats.images[Math.floor(Math.random()*cats.images.length)];

  if(remove) {
    cats.images.splice(cat, 1);
  }
  return cat
}

const catLeft = newCat(true);
const catRight = newCat(false);

const vote = function() {

}

// console.log(cats.images)
</script>

<style scoped>
  .acat {
    border-radius: 50px;
    height: 300px;
    object-fit: cover;
  }
</style>
