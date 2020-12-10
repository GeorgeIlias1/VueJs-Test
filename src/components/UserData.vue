<template>
  <div>
    <form @submit.prevent="addUser">
      <div>
        <label>Username</label>
        <input type="text" v-model="enteredName">
      </div>
      <div>
        <label>Age</label>
        <input type="number" v-model="enteredAge">
      </div>
      <div>
        <button>Add User</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  emits: ['add-user'],
  data() {
    return {
      enteredName: '',
      enteredAge: ''
    };
  },
  methods: {
    addUser() {
      this.$emit('add-user', this.enteredName, this.enteredAge);
    }
  }
};
</script>
