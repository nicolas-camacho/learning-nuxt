<template>
  <div>
    <h2>Welcome to AppJokes</h2>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Welcome",
      meta: [
        {
          hid: "welcome",
          name: "welcome",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>
