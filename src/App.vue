<template>
    <h1>{{ greet }} {{ name }}</h1>
    <h2 v-html="channel"></h2>
    <h2 :id="headingId">Heading</h2>
    <button :disabled="isDisabled">Hello world</button>
    <h2 class="underline">Underline Text</h2>
    <h2 :class="status">Status</h2>
    <h2 :class="isPromoted ? 'promoted' : ''">promoted Movie</h2>
    <h2 :class="isSoldOut ? 'sold-out' : 'new'">Sold Out Movie</h2>
    <h2 :class="isPromoted ? ['new', 'promoted'] : 'sold-out'">Newly Promoted Movie</h2>
    <h2 :class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut
    }">Object conditional Movie</h2>

    <h2 :style="{
      color: highlightColor,
      fontSize: size+'px',
      padding: '20px',
      border: '1px solid red'
    }">Inline Style</h2>

    <h2 :style="styleObject">Another Style</h2>

    <h1 :style="[baseStyle, successStyle]">Another of another style</h1>

    
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
      isSoldOut: true,
      highlightColor: 'orange',
      size: 50,
      styleObject: {
        color: 'blue',
        fontSize: '90px',
        padding: '10px',
        border: '1px solid yellow'
      },
      baseStyle: {
        fontSize: '30px',
        fontWeight: 'bold'
      },
      successStyle: {
        color: 'green',
        backgroundColor: 'black',
        border: '1px solid red'
      }
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
