<template>
  <h1>Welcom to admin page</h1>
</template>

<script>
export default {
  layout: "admin",
  middleware: ["admin-auth"],
};
</script>

<style lang="sass" scoped>

</style>