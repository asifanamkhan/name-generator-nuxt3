<template>
  <div class="container">
    <h1>Name Generator</h1>
    <p>1) Choose your option and click "Find Name" bellow</p>
    <div class="options-container">
      <div class="option-container">
        <h4>choose a gender</h4>
        <div class="option-buttons">
          <button
              class="option-btn btn-left"
              :class="options.gender === Gender.MALE && 'option-active'"
              @click="options.gender = Gender.MALE"
          >Male
          </button>
          <button class="option-btn"
                  :class="options.gender === Gender.GIRL && 'option-active'"
                  @click="options.gender = Gender.GIRL"
          >Female
          </button>
          <button class="option-btn btn-right"
                  :class="options.gender === Gender.UNISEX && 'option-active'"
                  @click="options.gender = Gender.UNISEX"
          >Unisex
          </button>
        </div>
      </div>
      <div class="option-container">
        <h2>2) Choose the names popularity</h2>
        <div class="option-buttons">
          <button class="option-btn btn-left"
                  :class="options.popularity === Popularity.TRENDY && 'option-active'"
                  @click="options.popularity = Popularity.TRENDY"
          >Trendy
          </button>
          <button class="option-btn btn-right"
                  :class="options.popularity === Popularity.UNIQUE && 'option-active'"
                  @click="options.popularity = Popularity.UNIQUE"
          >Unique
          </button>
        </div>
      </div>
      <div class="option-container">
        <h2>3) Choose length here</h2>
        <div class="option-buttons">
          <button class="option-btn btn-left"
                  :class="options.length === Length.LONG && 'option-active'"
                  @click="options.length = Length.LONG"
          >Long
          </button>
          <button class="option-btn"
                  :class="options.length === Length.SHORT && 'option-active'"
                  @click="options.length = Length.SHORT">Short
          </button>
          <button class="option-btn btn-right"
                  :class="options.length === Length.ALL && 'option-active'"
                  @click="options.length = Length.ALL">All
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

let name: string = "anam";

enum Gender{
  GIRL = 'Girl',
  MALE = 'Male',
  UNISEX = 'Unisex',
}

enum Popularity{
  TRENDY = 'Trendy',
  UNIQUE = 'Unique',
}

enum Length{
  LONG = 'Long',
  SHORT = 'Short',
  ALL = 'All',
}

interface OptionState {
  gender: Gender,
  popularity: Popularity,
  length: Length,
}

const options = reactive<OptionState>({
  gender: Gender.MALE,
  popularity: Popularity.TRENDY,
  length: Length.ALL,
})
</script>


<style scoped>
.container {
  font-family: Kalpurush;
  color: rgb(27, 60, 138);
  max-width: 50rem;
  margin: auto;
  text-align: center;
}

h1 {
  font-size: 3rem;
}

.options-container {
  background-color: rgb(255, 238, 236);
  border-radius: 2rem;
  padding: 1rem;
  width: 95%;
  margin: 0 auto;
  margin-top: 2rem;
  position: relative;
}

.option-container {
  margin-bottom: 2rem;
}

.option-btn {
  background-color: white;
  outline: 0.15rem solid rgb(249, 87, 89);
  border: none;
  padding: 0.75rem;
  width: 12rem;
  font-size: 1rem;
  font-weight: 200;
  color: rgb(27, 60, 138);
  cursor: pointer;
}

.btn-left {
  border-radius: 1rem 0 0 1rem;
}

.btn-right {
  border-radius: 0 1rem 1rem 0;
}

.option-active {
  background-color: rgb(249, 87, 89);
  color: white;
}

</style>
