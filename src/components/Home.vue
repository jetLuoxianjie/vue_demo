<template>
  <div class="hello">
    {{msg}}
    <el-button type="primary" @click="hello('啊啊啊')" round>主要按钮</el-button>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      msg: "Welcome to Home"
    };
  },
  methods: {
    hello: function(e) {
      this.$axios
        .get("/api/hello")
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->


<style scoped>
h1,
h2 {
  font-weight: normal;
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
