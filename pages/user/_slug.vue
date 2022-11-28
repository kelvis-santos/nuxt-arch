<template>
  <h1>{{ this.slug }}</h1>
</template>
  
  <script>
export default {
  async asyncData({ params }) {
    const slug = params.slug; // Quando estiver chamando /abc o slug será "abc"
    return { slug };
  },
};
</script>