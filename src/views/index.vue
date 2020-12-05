<template>
  <div class="home">
    <Navigator />
    <Main />
  </div>
</template>

<script>
import Navigator from "../components/Navigator";
import Main from "../components/Main";

export default {
  name: "Home",
  components: {
    Navigator,
    Main
  }
};
</script>
