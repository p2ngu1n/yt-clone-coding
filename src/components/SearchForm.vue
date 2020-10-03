<template>
  <nav class="navbar navbar-expand-sm bg-light" style="margin-bottom: 2rem">
    <div class="container">
      <img src="../assets/yt_logo_rgb_light.png" style="width: 7rem" />
      <form class="form-inline">
        <input
          v-model="searchString"
          @keydown.13.prevent="parseSearchString"
          type="text"
          class="form-control"
          placeholder="Search"
        />
        <div class="input-group-append">
          <button
            @click="parseSearchString"
            class="btn btn-outline-secondary"
            type="button"
          >
            <i class="fas fa-search"></i>
          </button>
        </div>
      </form>
    </div>
  </nav>
</template>

<script>
export default {
  name: "SearchForm",
  data() {
    return {
      searchString: "",
    };
  },
  methods: {
    parseSearchString() {
      const trimmedSearchString = this.searchString.trim();

      if (trimmedSearchString !== "") {
        const searchParams = trimmedSearchString.split(/\s+/);
        this.$emit("search", searchParams);
        this.searchString = "";
      }
    },
  },
};
</script>

<style scoped>
input,
button {
  box-shadow: none !important;
  background-color: #fff;
}

.form-control {
  border-color: #6c757d;
}
</style>