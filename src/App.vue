<template>
  <h2>Contact List</h2>
  <ul>
    <!-- <li v-for="friend in friends" :key="friend.id">
      {{ friend.name }}
    </li> -->
    <friend-contact></friend-contact>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 1,
          name: "Aaron",
          phone: "123-456-7890",
          email: "aaron@example.com",
        },
        {
          id: 2,
          name: "Blake",
          phone: "234-567-8901",
          email: "blake@example.com",
        },
        {
          id: 3,
          name: "Caleb",
          phone: "345-678-9012",
          email: "caleb@example.com",
        },
      ],
    };
  },
};
</script>
