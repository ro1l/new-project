<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
  <button type="button" class="btn btn-primary">Primary</button>
  <VForm v-slot="{ errors, values, validate }" @submit="onSubmit">
    {{ errors }} {{ values }}
    <div class="mb-3">
      <label for="email" class="form-label">
        <VField id="email" name="email" type="email"
      class="form-control" :class="{ 'is-invalid': errors['email'] }"
      placeholder="請輸入 Email" rules="email|required" v-model="user.email"></VField>
      Email</label>
      <error-message name="email" class="invalid-feedback"></error-message>
    </div>
    <button class="btn me-2 btn-outline-primary" type="button" @click="validate">驗證</button>
    <button class="btn btn-primary" type="submit">Submit</button>
    </VForm>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
  },
  data() {
    return {
      user: {},
    };
  },
  methods: {
    onSubmit() {
      console.log(this.user);
    },
  },
  created() {
    console.log(this);
  },
};
</script>
