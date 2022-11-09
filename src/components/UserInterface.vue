<template>
  <div>
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png" />
    <h1>Articles</h1>
    <input type="text" placeholder="Filter" v-model="query" />
    <SearchDlg :query="query" />
  </div>
</template>

<script>
import { ref } from 'vue';
import SearchDlg from './SearchDlg.vue';

export default {
  components: {
    SearchDlg,
  },
  setup() {
    const query = ref('');

    return {
      query,
    };
  },
};
</script>

<style scoped>
img {
  width: 5em;
}
</style>
