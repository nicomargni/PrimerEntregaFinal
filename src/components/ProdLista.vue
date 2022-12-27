<template>
  <div>
    <div>
      <div class="card" style="width: 18rem">
        <img class="card-img-top" :src="imagen" alt="" />
        <div class="card-body">
          <h5 class="card-title">{{ titulo }}</h5>
          <p class="card-text">
            $<strong>{{ costo }}</strong>
          </p>
          <button v-if="stock" class="btn btn-primary">Comprar</button>
          <p v-else>Sin stock</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProdLista",
  props: {
    titulo: String,
    imagen: String,
    costo: Number,
    stock: Boolean,
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