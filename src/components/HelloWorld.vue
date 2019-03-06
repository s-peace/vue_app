<template>
  <div class="hello">
    <h1>{{title}}</h1>
    <p>{{message}}</p>
    <hr>
    <div>
      <input type="text" v-model="input">
      <button v-on:click="doAction">
        Click
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
  },
  data: function(){
    return {
      message: 'waz ur name?',
      input: 'no-name',
    };
  },
  methods: {
    doAction: function(){
      this.message = 'hi ' + this.input + 'san!';
      this.$emit('result-event',this.input);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  margin: 0;
  padding: 0;
  text-align: left;
}
h1 {
  font-size: 72px;
  font-weight: bold;
  text-align: center;
  letter-spacing: -8px;
  color: #f0f0f0;
  margin: 0;
}
p {
  margin: 0;
  color: #666;
  font-size: 16px;
}
</style>
