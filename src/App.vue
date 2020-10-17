<template>
  <div id="app" tabindex="0" @keydown.alt.prevent="toggle">
    <div v-if="showEditor" style="margin-bottom: 100px">
      <h5>press alt(Option) to hide editor</h5>
      <label for="border" style="font-weight: bold; margin-right: 1em"
        >Border?</label
      >
      <input id="border" type="checkbox" v-model="border" />
      <div v-for="k in Object.keys(art)" :key="k">
        <label style="font-weight: bold; margin-right: 1em" :for="k">{{
          k
        }}</label>
        <input
          :id="k"
          type="text"
          v-model="art[k]"
          v-if="k !== 'description'"
        />
        <textarea
          v-else
          v-model="art[k]"
          :id="k"
          cols="30"
          rows="10"
        ></textarea>
      </div>
    </div>

    <ArtLabel ref="label" :border="border" :art="art" />
  </div>
</template>

<script>
import ArtLabel from "./components/ArtLabel.vue";

export default {
  name: "App",
  components: {
    ArtLabel,
  },
  methods: {
    toggle() {
      this.showEditor = !this.showEditor;
    },
  },
  data: function () {
    return {
      border: true,
      showEditor: true,
      art: {
        artistName: "Wayne Thiebaud",
        artistBorn: "(b. 1920)",
        title: "Diagonal Freeway",
        year: "1992",
        medium: "Acrylic on canvas",
        description:
          "Partial gift of Morgan Flagg in memory of his son Lawrence",
      },
    };
  },
};
</script>

<style lang="scss">
#app {
  margin: 0px;
}
label {
  width: 200px;
  display: inline-block;
}
</style>
