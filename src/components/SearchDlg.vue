<template>
  <div>
    <ul>
      <li v-for="(item, index) in filteredItems" :key="index">
        {{ item.Name }}
      </li>
    </ul>
  </div>
</template>

<script>
import titles from '../post-data.json';
import { computed } from 'vue';

export default {
  props: {
    query: { type: String, required: true },
  },
  setup(props, context) {
    const filteredItems = computed(() => {
      return titles.filter((s) =>
        s.Name.toLowerCase().includes(props.query.toLowerCase())
      );
    });
    return {
      filteredItems,
    };
  },
};
</script>

<style scoped></style>
