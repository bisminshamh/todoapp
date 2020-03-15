<template>
  <div>
    <HelloWorld msg="TODO APP" />
    <buttons />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import buttons from "@/components/buttons.vue";

export default {
  components: {
    HelloWorld,
    buttons
  }
};
</script>
<style lang="sass"></style>
