<template>
  <div id="app">
    {{data}}
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      data: {}
    }
  },
  beforeMount(){
    this.getName();
  },
  methods: {
    async getName(){
      const res = await fetch('https://api.agify.io/?name=michael');
      const data = await res.json();
      this.data = data;
    }
  }
};
</script>
