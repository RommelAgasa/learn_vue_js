<template>


  <!--- Conditional Rendering -->
  <h2 v-if="num === 0">The number is zero.</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>Not number.</h2>

  <template v-if="display">
    <h2>Rommel</h2>
    <h2>Learning</h2>
    <h2>Vue</h2>
  </template>


  <h2 v-show="showElement">Using v-show</h2>
  <h2 v-if="showElement">Using v-if</h2> <!-- set the showElement to false and inspect element --->

  <div>
    <h1>{{ firstName }} {{ lastName }}</h1>
    <p>Age: {{ age }}</p>
  </div>
  <div v-text="address.city + ', ' + address.province"></div>
  <div v-html="hack"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Click Me</button>
  <h2 class="underline">Underline text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>

  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Sold Out Movie</h2>
  <h2 v-bind:class="['new', 'promoted']">Newly Promoted Movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array Conditional Movie</h2>

  <h2 v-bind:class="{
    promoted: isPromoted,
    new: !isSoldOut,
    'sold-out': isSoldOut
  }">Object Conditional Movie</h2>


  <h2 v-bind:style="{
    color: highlightColor,
    fontSize: headerSize + 'px',
    padding: '20px'
  }">Inline Style</h2>

  <h2 v-bind:style="headerStyleObject">Style Object</h2>

  <!--- you can remove the v-bind-->
  <div :style="[baseStyleObject, successStyleObject]">Success Style</div>

  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>


  <ListRenderingView></ListRenderingView>
  <hr>
  <Methods></Methods>
  <hr>
  <EventHandling></EventHandling>
  <hr>
  <FormHandling></FormHandling>
  <hr>
  <ComputedProperties></ComputedProperties>
  <hr>
  <LearnWatchers></LearnWatchers>

</template>

<script>
import ListRenderingView from './components/ListRendering.vue';
import Methods from './components/LearnMethods.vue';
import EventHandling from './components/EventHandling.vue';
import FormHandling from './components/FormHandling.vue';
import ComputedProperties from './components/ComputedProperties.vue';
import LearnWatchers from './components/LearnWatchers.vue';




export default {
  name: 'App',
  components: {
    ListRenderingView,
    Methods,
    EventHandling,
    FormHandling,
    ComputedProperties,
    LearnWatchers
  },
  data(){
    const obj = {
      firstName: "Rommel",
      lastName: "Agasa",
      age: 25,
      address:{
        city: "Sorsogon City",
        province: "Sorsogon",
      },
      channel: "<b>Rommel's Channel</b>",
      hack: '<a href="#" onclick="alert(\'You have been hacked!\')">Win a prize!</a>',
      headingId: 'heading',
      isDisabled: true,
      status: 'danger',
      isPromoted: true,
      isSoldOut: true,

      highlightColor: 'orange',
      headerSize: 50,

      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px'
      },

      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },

      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px',
      },

      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
        marginTop: '10px',
      },


      // -------------------------------------
      num: 0,
      display: true,
      showElement: true,

    }
    return obj;
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

.underline{
  text-decoration: underline;
}

.promoted{
  font-style: italic
}

.new{
  color:olivedrab
}

.sold-out{
  color: crimson
}

</style>
