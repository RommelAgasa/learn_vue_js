<template>
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

</template>

<script>


export default {
  name: 'App',
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
      }

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
