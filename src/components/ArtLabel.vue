<template>
  <div class="label" :class="{ border: border }">
    <h1 class="artist">
      {{ art.artistName }}
      <span class="born">{{ art.artistBorn }} </span>
    </h1>
    <h2 class="artwork">
      {{ art.title }}, <span class="year">{{ art.year }}</span>
    </h2>
    <h3 class="medium">{{ art.medium }}</h3>
    <pre class="description">{{ art.description }}</pre>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    art: Object,
    border: Boolean,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.artist {
  font-size: 24px;
  margin: 0;
  padding: 0;
  font-weight: bold;
}

.born,
.year {
  font-weight: normal;
  font-style: normal;
}

.artwork {
  font-size: 24px;
  font-style: oblique;
  margin: 8px 0;
}
.medium {
  font-size: 18px;
  font-weight: normal;
  margin-top: -2px;
  padding: 0 2px;
}
.description {
  letter-spacing: -0.2px;
  padding: 0 2px;
  word-break: break-all;
  font-size: 14px;

  font-family: Helvetica, sans-serif;
}
.label {
  font-family: Helvetica, sans-serif;
  box-sizing: border-box;
  padding: 24px;
  color: #000;
  background: #fff;
  display: inline-block;
  // background: url("../art.png");
  min-width: 490px;
  min-height: 350px;
  font-size: 14px;
}
.border {
  border: dashed 1px #ddd;
}
</style>
