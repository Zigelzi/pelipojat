<template>
  <div class="card f-grow">
    <h1 class="card-title mb-s">{{ title }}</h1>
    <p
      class="card-subtext text-capitalized"
      v-for="(task, index) in subtext"
      :key="index"
    >
      {{ task }}
    </p>
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    subtext: Array,
  },
}
</script>
<style lang="scss">
.card {
  max-width: 250px;
  background: var(--gray-100);
  margin: 0 var(--mg-m) var(--mg-m) 0;
  padding: var(--p-m);
}

.card-title {
  font-size: var(--text-20);
}

.card-subtext {
  color: var(--gray-400);
  font-size: var(--text-12);
  display: inline-block;
  margin: 0 var(--mg-s) 0 0;
}
</style>
