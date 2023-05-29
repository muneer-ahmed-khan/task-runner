<template>
  <div class="container">
    <Header
      @toggle-add-task="toggleAddTask"
      title="Task Tracker"
      :showAddTask="showAddTask"
    />

    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  name: "App",

  components: {
    Header,
    Footer,
  },

  data() {
    return {
      showAddTask: false,
    };
  },

  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Poppins" sans-serif;
}
.container {
  max-width: 500px;
  min-height: 300px;
  overflow: auto;
  border: 1px solid steelblue;
  padding: 30px;
  margin: 30px auto;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background-color: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}
</style>
