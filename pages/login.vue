<template>
  <section>
    <div v-if="$route.query.message" class="alert alert-danger mb-3">
      Залогинься
    </div>
    <form @submit.prevent="onSubmit">
      <h1>Введите логин</h1>

      <div class="form-group">
        <input class="form-control" type="text">
      </div>

      <p>
        <nuxt-link to="/">
          Домой
        </nuxt-link>

      </p>

      <button class="btn btn-primary">Login</button>
    </form>
  </section>
</template>

<script>
  export default {
    layout: 'empty',
    methods: {
      onSubmit() {
        this.$store.dispatch('login');
        this.$router.push('/');
      }
    }
  }
</script>

<style scoped>
  form {
    width: 500px;
    margin: 0 auto;
  }
</style>
