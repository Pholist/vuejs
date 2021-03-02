<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name</label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label>Phone</label>
      <input type="tel" v-model="enteredPhone" />
    </div>
    <div>
      <label>E-Mail</label>
      <input type="email" v-model="enteredAddress" />
    </div>
    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "NewFriend",
  data() {
    return {
      enteredName: "",
      enteredAddress: "",
      enteredPhone: "",
    };
  },
  methods: {
    submitData() {
      this.$emit(
        "submit-data",
        this.enteredName,
        this.enteredPhone,
        this.enteredAddress
      );
    },
  },
};
</script>
