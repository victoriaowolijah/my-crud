<template>
  <div id="app">
    <div class="ui fixed inverted menu vue-color">
      <div class="ui container">
        <a href="#" class="header item">vue js with laravel</a>
      </div>
    </div>

    <div class="ui main container">
        <MyForm />
        <CustomerList />
    </div>

  </div>
</template>

<script>
import MyForm from './components/MyForm.vue'
import CustomerList from './components/CustomerList.vue'

export default {
  name: 'App',
  components: {
    MyForm,
    CustomerList
  }
};
</script>

<style>
.vue-color {
  background: #82c6ee !important;
}

.main.container {
  margin-top: 60px;
}

.submit-button {
  margin-top: 25px !important;
  float: right;
}
</style>
