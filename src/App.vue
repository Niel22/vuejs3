<template>
    <h1>{{ greet }} {{ name }}</h1>
    <h2 v-html="channel"></h2>
    <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisabled">Hello world</button>
    <h2 class="underline">Underline Text</h2>
    <h2 v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPromoted ? 'promoted' : ''">promoted Movie</h2>
    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Sold Out Movie</h2>
    <h2 v-bind:class="isPromoted ? ['new', 'promoted'] : 'sold-out'">Newly Promoted Movie</h2>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      greet: "Hello",
      name: "Daniel",
      channel: "<b>NIEL</b>",
      headingId: "heading",
      isDisabled: true,
      status: "danger",
      isPromoted: true,
      isSoldOut: false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab
}

.sold-out {
  color: red
}
</style>
