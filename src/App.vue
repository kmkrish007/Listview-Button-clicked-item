<template>
  <div id="app">
    <Listview/>
  </div>
</template>

<script>
import Listview from "./components/Listview";

export default {
  name: "App",
  components: {
    Listview
  }
};
</script>

<style>
#app {
  height: 100%;
}
</style>
