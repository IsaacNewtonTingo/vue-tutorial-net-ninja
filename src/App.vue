<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Signup</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja giveaway</h1>
      <p>Grab goodies at 1/2 the price</p>
    </Modal>
  </div>
  <br />
  <button @click.alt="toggleModal">open modal</button>
</template>

<script>
import Modal from "./components/modal-main.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "Boom",
      header: "sign title",
      content: "Hello ninjas",
      theme: "sale",
      showModal: false,
    };
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  color: blue;
}
</style>
