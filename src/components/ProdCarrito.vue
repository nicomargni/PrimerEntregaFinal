<template>
  <div>
    <div>
      <h4>{{titulo}}</h4>
      <p>${{precio}}</p>
    </div>

  </div>
</template>

<script>
export default {
  name: "ProdCarrito",
  props:{
    titulo:String,
    precio:Number
  },

  data() {
    return {
    };
  },

  methods: {},
};
</script>
<style scoped>

</style>