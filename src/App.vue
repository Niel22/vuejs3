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

    <h2 v-if="num === 0">The number is zero</h2>
    <h2 v-else-if="num < 0">The number is negative</h2>
    <h2 v-else-if="num > 0">The number is Positive</h2>
    <h2 v-else>Not a number</h2>

    <template v-if="display">
      <h2>Hello</h2>
      <h2>Hi</h2>
      <h2>Wassup</h2>
    </template>

    <h2 v-show="display">Use V Show</h2>

    <h2 v-for="(name, index) in names" :key="name">{{ index+1 }} {{ name }}</h2>

    <h2 v-for="(name, index) in fullnames" :key="index">{{ index + 1 + '-' }} {{ name.first }} {{ name.last }}</h2>

    <div v-for="actor in actors" :key="actor.name">
      <h2>{{ actor.name }}</h2>
      <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
    </div>

    <h2  :key="value"><span style="text-transform: capitalize;">{{ key }}</span>: {{ value }}</h2>

    <template v-for="(value, key) in info" :key="value">
      <h2>{{ key }}</h2>
      <hr>
      <p>{{ value }}</p>
      <br><br>
    </template>


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
      },
      num: "Hello",
      display: true,
      names: [
        'bruce', 'john', 'diana'
      ],
      fullnames: [
        {first: 'James', last: "Daniel"},
        {first: 'NI', last: "EL"},
        {first: 'Moses', last: "David"}
      ],
      actors: [
        {
          name: "Title Sample",
          movies: ['movie 1', 'movie 2']
        },
        {
          name: "Title Sample",
          movies: ['movie 1', 'movie 2']
        },
        {
          name: "Title Sample",
          movies: ['movie 1', 'movie 2']
        }
      ],
      info: {
        name: "James",
        age: 20,
        level: "Intermediate"
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
