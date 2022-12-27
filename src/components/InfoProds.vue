<template>
  <div>
    <div class="card">
      <div class="card-body">
        <h2><strong>{{titulo}}</strong></h2>
        <p>{{descripcion}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoProds",
  props:{
    titulo:String,
    descripcion:String
  },

  data() {
    return {};
  },

  methods: {},
};
</script>

<style scoped>
.card{
    background-color: pink;
}
</style>