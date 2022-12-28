<template>
  <div>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">ID</th>
          <th scope="col">Nombre</th>
          <th scope="col">Precio</th>
          <th scope="col"></th>
          <th scope="col">Total</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>GTA V</td>
          <td>$1200</td>
          <td><button>Quitar</button></td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Batman Arkham City</td>
          <td>$1200</td>
          <td><button>Quitar</button></td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td></td>
          <td></td>
          <td></td>
          <td>$2400</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "ProdCarrito",
  props: {
  },

  data() {
    return {};
  },

  methods: {},
};
</script>
<style scoped>
</style>