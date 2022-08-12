<template>
  <h1>vue xss poc</h1>
  <div class="poc">
    <p class="string">into v-html : <span v-html="inputString"></span></p>
    <input
      class="input1"
      v-model="inputString"
      placeholder="input your string"
    />
  </div>
  <br />
  <div class="poc2">
    <p class="string">into v-bind : {{ userProvidedUrl }}</p>
    <a v-bind:href="userProvidedUrl"> Click Me </a>
    <br />
    <input
      class="input2"
      v-model="userProvidedUrl"
      placeholder="input your url"
    />
  </div>
  <br />
  <a
    href="https://github.com/fujiokayu/vue-xss-poc"
    target="_blank"
    rel="noopener"
    >repository</a
  >
</template>

<script>
export default {
  data() {
    console.log(process.env.HONEY_CREDENTIALS);
    return {
      inputString: "",
      userProvidedUrl: "",
    };
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
