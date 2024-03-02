<template>
  <section>
    <h2>My Friends</h2>
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
