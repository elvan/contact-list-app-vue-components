<template>
  <form @submit.prevent="submitData">
    <div>
      <label for="name">Name</label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label for="phone">Phone</label>
      <input type="tel" v-model="enteredPhone" />
    </div>
    <div>
      <label for="email">Email</label>
      <input type="email" v-model="enteredEmail" />
    </div>
    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ["add-contact"],

  data() {
    return {
      enteredName: "",
      enteredPhone: "",
      enteredEmail: "",
    };
  },

  methods: {
    submitData() {
      this.$emit("add-contact", {
        name: this.enteredName,
        phone: this.enteredPhone,
        email: this.enteredEmail,
      });

      this.enteredName = "";
      this.enteredPhone = "";
      this.enteredEmail = "";
    },
  },
};
</script>

<style>
</style>
