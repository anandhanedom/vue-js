<template>
  <div>
    <!-- <div>{{ greet }} {{ name }}</div>
    <div v-text="channel"></div>
    <div v-html="channel"></div> -->

    <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
    <h2 class="underline">Underlined text</h2>
    <h2 class="underline" v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2 v-bind:class="['new', 'promoted']">Newly promoted movie</h2>
    <h2
      v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']"
    >
      Array conditional movie
    </h2>
    <h2
      v-bind:class="{
        promoted: isPromoted,
        new: !isSoldOut,
        'sold-out': isSoldOut,
      }"
    >
      Object conditional movie
    </h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      // name: "John Doe",
      // greet: "Hello",
      // channel: "<b>Codevolution</b>",
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: false,
      isSoldOut: false,
    };
  },
};
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

.success,
.new {
  color: green;
}

.danger,
.sold-out {
  color: red;
}

.promoted {
  font-style: italic;
}
</style>
