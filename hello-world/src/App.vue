<template>
  <div>
    <!-- <div>{{ greet }} {{ name }}</div>
    <div v-text="channel"></div>
    <div v-html="channel"></div> -->

    <h2 :id="headingId">Heading</h2>
    <button :disabled="isDisabled">Bind</button>
    <h2 class="underline">Underlined text</h2>
    <h2 class="underline" :class="status">Status</h2>
    <h2 :class="isPromoted && 'promoted'">Promoted movie</h2>
    <h2 :class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
    <h2 :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">
      Array conditional movie
    </h2>
    <h2
      :class="{
        promoted: isPromoted,
        new: !isSoldOut,
        'sold-out': isSoldOut,
      }"
    >
      Object conditional movie
    </h2>
    <h2
      :style="{
        color: highlightColor,
        fontSize: headerSize + 'px',
        padding: '20px',
      }"
    >
      Inline style
    </h2>
    <h2 :style="headerStyleObj">Style obj</h2>
    <div :style="[baseStyleObj, successStyleObj]">Success style</div>
    <div :style="[baseStyleObj, dangerStyleObj]">Danger style</div>
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
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObj: {
        color: "orange",
        fontSize: "50px",
        padding: "20px",
      },
      baseStyleObj: {
        fontSize: "50px",
        padding: "20px",
      },
      successStyleObj: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
      },
      dangerStyleObj: {
        color: "darkred",
        backgroundColor: "red",
        border: "1px solid darkred",
      },
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
