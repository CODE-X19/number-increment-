<template>
  <div class="card">
    <h2 class="name">Vikkywise project</h2>
    <h4 id="counter">{{ count }}</h4>
    <div class="container">
      <button class="counterBtn prevBtn" @click="decrement">Lower</button>
      <button class="counterBtn nextBtn" @click="increment">Add</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    }
  },
  watch: {
    count(newValue) {
      if (newValue < 0) {
        document.getElementById('counter').style.color = 'red';
      } else if (newValue > 0) {
        document.getElementById('counter').style.color = 'green';
      } else {
        document.getElementById('counter').style.color = '#333';
      }
    }
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body,
html {
  display: grid;
  min-height: 100%;
  place-items: center;
  background-color: antiquewhite;
}

.card {
  width: 600px;
  height: 350px;
  box-shadow: 10px 10px 15px rgb(192, 183, 183), -10px -10px 15px rgb(192, 183, 183);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
}

.name {
  font-size: 3rem;
}

#counter {
  font-size: 5rem;
  margin-bottom: 1rem;
}

.prevBtn,
.nextBtn {
  font-size: 1.3rem;
  outline: none;
  padding: 0.7rem 1.5rem;
  cursor: pointer;
  margin: 0 2rem;
  background-color: black;
  color: aliceblue;
  border: none;
  border-radius: 5px;
}
</style>
