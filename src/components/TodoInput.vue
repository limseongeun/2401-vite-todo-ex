<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" @keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>

     <Modal :show="showModal">
      <template #header>
        <h3>경고!</h3>
      </template>

      <template #body>
        <p>아무것도 입력하지 않으셨습니다.</p>
      </template>

      <template #footer>
        <button
          class="modal-default-button"
          @click="showModal = false"
        >닫기</button>
      </template>
    </Modal>
  </div>
</template>

<script>
import Modal from './common/Modal.vue'

export default {
  data() {
    return {
      newTodoItem: "",
      showModal: false
    }
  },
  methods: {
    addTodo() {
      if(this.newTodoItem !== '') {
        this.$store.commit('addOneItem', this.newTodoItem);
        this.clearInput();
      } else {
        this.showModal = !this.showModal;
      }
    },
    clearInput() {
      this.newTodoItem = '';
    }
  },
  components: {
    Modal
  }
}
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  padding: 0 0.9rem;
  border-style: none;
  font-size: 0.9em;
}
.addContainer {
  display: block;
  float: right;
  width: 3rem;
  background: linear-gradient(to right, #6478FB, #8763FB);
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>