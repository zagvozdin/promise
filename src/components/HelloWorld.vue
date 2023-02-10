<template>
  <div class="hello">
    <p>{{ msg }}</p>
    <button @click="start()">Start</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  methods: {
    async start() {
      console.log("Start pressed");
      console.log(await this.one());
      console.log(await this.two());
      console.log(await this.three());
      console.log(await this.four());
    },
    async one() {
      console.log("insise ONE begin");
      return new Promise((res) => {
        setTimeout(() => res(1), 2000);
      });
    },
    async two() {
      console.log("insise TWO begin");
      return new Promise((res) => {
        setTimeout(() => res(2), 2000);
      });
    },
    async three() {
      console.log("insise THREE begin");
      return new Promise((res) => {
        setTimeout(() => res(3), 2000);
      });
    },

    async four() {
      console.log("inside FOUR begin");
      const p = new Promise((res) => {
        setTimeout(() => res(4), 2000);
      });
      return p.then((res) => {
        return res;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
