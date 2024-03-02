<template>
  <section>
    <h2>My Friends</h2>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 'melvin',
          name: 'Melvin Jenkins',
          phone: '01234 5678 991',
          email: 'melvin@localhost.com',
        },
        {
          id: 'jessica',
          name: 'Jessica Weber',
          phone: '09876 543 221',
          email: 'jessica@localhost.com',
        },
      ],
    };
  },
};
</script>
