<template>
  
  <li>
    <h2 @click="toggleFavorite">{{ name }} {{isFavorite ? 'favorite' : ''}}</h2>
    <button @click="toggleDetails">Details</button>
    <button @click="$emit('delete',id)">Delete</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
    </ul>
  </li>
  
</template>

<script>
export default {
 name:"FriendContact",
 props: ["name", "phoneNumber", "emailAddress","isFavorite","id"],
  data(){
     return{
       detailsAreVisible:false,
     };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite(){
    this.$emit('toggle-favorite',this.id)
    }
  }
};
</script>