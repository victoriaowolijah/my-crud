<template>
  <div id="app">
    <div class="vic__container">
      <div class="vic__row">
        <div class="vic__col__12">
          <div class="vic__new__post__section">
            <!-- <div class="vic__new__post__button__section" v-if="componentButton">
              <button class="vic__new__post__button" v-on:click="showForm">New Post</button>
            </div> -->
            <div class="vic__component__section">
              <component v-bind:is="component" />
            </div>
          </div>
          <!-- <BlogForm />
          <BlogList />
          <BlogDetail /> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import MyForm from './components/MyForm.vue'
// import CustomerList from './components/CustomerList.vue'
import BlogForm from './components/BlogForm.vue'
// import BlogDetail from './components/BlogDetail.vue'
import BlogList from './components/BlogList.vue'
import './components/style.css'
import './components/blog.css'

export default {
  name: 'App',
  components: {
    // MyForm,
    // CustomerList,
    BlogForm,
    BlogList,
    // BlogDetail,
  },
  data() {
    return {
      component: "BlogList",
      componentButton: true
    }
  },
  methods: {
    showForm() {
      if (this.component === BlogList) {
        this.component = BlogForm;
        this.componentButton = false;
      } else if (this.component === BlogForm) {
        this.component = BlogList;
        this.componentButton = true;
      }
      else {
        this.component = BlogList;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
