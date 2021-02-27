<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        name="title"
        v-model="title"
        placeholder="Add Task..."
      />
      <input type="submit" value="submit" class="btn" />
    </form>
  </div>
</template>
<script>
// imports
import { v4 } from 'uuid';
export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    };
  },
  methods: {
    addTodo(e) {
      console.log('clicked');
      e.preventDefault();
      const newTodo = {
        id: v4(),
        title: this.title,
        completed: false,
      };
      //  send to parent
      this.$emit('addTodo', newTodo);
      this.title = '';
    },
  },
};
</script>
<style scoped>
form {
  display: flex;
  margin-bottom: 10px;
}
input[type='text'] {
  flex: 10;
  padding: 5px;
}
input[type='submit'] {
  flex: 2;
}
</style>
