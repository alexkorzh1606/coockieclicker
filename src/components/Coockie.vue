<template>
  <div class="coockie">
    <h1>Кликните по изображению печеньки</h1>
    <img v-bind:src="coockie_element.img" v-on:click="clickCounter" alt="Здесь должна быть печенька, но кажется, она ушла =(((">
    <h2>Вы кликнули {{counter}} раз(а)</h2>
    <h2>Ваша следующая цель: кликнуть {{target}} раз</h2>
  </div>
</template>

<script>
export default {
  name: 'Coockie',
  data() {
    return {
      coockie_element: {
        img: 'https://image.flaticon.com/icons/png/512/614/614131.png', // переписать на ссылку в ассетс
      },
      counter: 0,
      target: 5,
    };
  },
  methods: {
    clickCounter() {
      if (this.counter === this.target - 1) {
        this.target *= 3;
      }
      this.counter += 1;
      console.log(this.counter);
      return this.counter;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.coockie {
  display: flex;
  flex-direction: column;
  align-items: center;
}
img{
  width: 200px;
}
h1, h2 {
  font-family: sans-serif;
}
</style>
