<template>
  <div>
    <form class="formulario col-6">
      <!-- Email input -->
      <div class="form-outline mb-4">
        <input type="email" id="form2Example1" class="form-control" :placeholder="user">
        <label class="form-label" for="form2Example1">Correo electronico</label>
      </div>

      <!-- Password input -->
      <div class="form-outline mb-4">
        <input type="password" id="form2Example2" class="form-control" />
        <label class="form-label" for="form2Example2">Password</label>
      </div>

      <!-- 2 column grid layout for inline styling -->
      <div class="row mb-4">
        <div class="col d-flex justify-content-center">
          <!-- Checkbox -->
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value=""
              id="form2Example31"
              checked
            />
            <label class="form-check-label" for="form2Example31">
              Remember me
            </label>
          </div>
        </div>

        <div class="col">
          <!-- Simple link -->
          <a href="#!">Forgot password?</a>
        </div>
      </div>

      <!-- Submit button -->
      <button type="button" class="btn btn-primary btn-block mb-4">
        Sign in
      </button>
    </form>
  </div>
</template>

<script>

export default {
  name: "LoginPrueba",
  data() {
    return {
        user: JSON.parse(localStorage.getItem("email"))

    };
  },
  

  methods: {
    
  },
};
</script>

<style scoped>
.formulario {
  display: inline-block;
}
</style>