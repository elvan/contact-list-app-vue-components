<template>
  <section>
    <header>
      <h1>My Friends</h1>
    </header>
    <new-friend @add-contact="addContact"></new-friend>
    <ul>
      <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :id="friend.id"
        :name="friend.name"
        :phone-number="friend.phone"
        :email-address="friend.email"
        :is-favorite="friend.isFavorite"
        @toggle-favorite="toggleFavoriteStatus"
        @delete="deleteContact"
      ></friend-contact>
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
          isFavorite: true,
        },
        {
          id: 'jessica',
          name: 'Jessica Weber',
          phone: '09876 543 221',
          email: 'jessica@localhost.com',
          isFavorite: true,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      const identifiedFriend = this.friends.find((friend) => friend.id === friendId);
      identifiedFriend.isFavorite = !identifiedFriend.isFavorite;
    },
    addContact(name, phone, email) {
      const newFriendContact = {
        id: new Date().toISOString(),
        name: name,
        phone: phone,
        email: email,
        isFavorite: false,
      };
      this.friends.push(newFriendContact);
    },
    deleteContact(friendId) {
      this.friends = this.friends.filter((friend) => friend.id !== friendId);
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');

* {
  box-sizing: border-box;
}
html {
  font-family: 'Jost', sans-serif;
}
body {
  margin: 0;
}
header {
  width: 90%;
  max-width: 40rem;
  margin: 3rem auto;
  padding: 1rem;
  border-radius: 10px;
  color: white;
  text-align: center;
  background-color: #58004d;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app li,
#app form {
  width: 90%;
  max-width: 40rem;
  margin: 1rem auto;
  padding: 1rem;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
#app h2 {
  margin: 0 0 1rem 0;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  font-size: 2rem;
}
#app button {
  padding: 0.05rem 1rem;
  border: 1px solid #ff0077;
  color: white;
  font: inherit;
  cursor: pointer;
  background-color: #ff0077;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
#app button:hover,
#app button:active {
  border-color: #ec3169;
  background-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
#app input {
  padding: 0.15rem;
  font: inherit;
}
#app label {
  display: inline-block;
  width: 7rem;
  margin-right: 1rem;
  font-weight: bold;
}
#app form div {
  margin: 1rem 0;
}
</style>
